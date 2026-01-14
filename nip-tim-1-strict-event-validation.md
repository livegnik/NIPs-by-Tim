



# NIP-TIM-1: Strict Event Validation

`draft` `optional` `client` `relay`

This NIP defines a strict, uniform validation pipeline for NIP-01 events, so clients and relays can make the same decision about what is valid, what is safe to store, and what is safe to render. It does not change the NIP-01 event format or message flow.

## Motivation

NIP-01 defines the event format, how `id` is derived, and how relays acknowledge acceptance or rejection.

In practice, different implementations apply different checks, in different orders, and sometimes only partially. This causes common issues:

* Clients generate events that some relays reject, because validation differs.
* Clients accept and render malformed events that should be rejected, causing crashes, broken threads, and security risks.
* Relays accept malformed tags or inconsistent types, which later break indexing, filtering, and downstream clients.
* Libraries implement "whatever worked with this relay" instead of "what the protocol says".

The goal of this NIP is to standardize a minimal, strict pipeline that is:

* deterministic
* cheap to run
* compatible with NIP-01 semantics
* implementable on the client first, without requiring changes from relays
* usable by relays as a predictable acceptance layer

## Status and scope

This NIP is optional. It specifies validation behavior that may be implemented by clients, relays, or both.

This NIP does not:

* introduce new event fields
* introduce new message types
* define new event kinds or tags
* define relay policy or moderation rules beyond validation
* require changes to signature algorithms or encodings

## Conventions and terminology

The key words MUST, MUST NOT, SHOULD, SHOULD NOT, and MAY are to be interpreted as described in RFC 2119.

* **Raw event**: a JSON object received from the network or constructed locally, not yet validated.
* **Validated event**: an event that passed all checks in this NIP, and is safe to store, index, and render.
* **Strict validation**: the full pipeline defined here.
* **Validation context**: local configuration and relay limits, such as maximum sizes or timestamp windows.

## Background, NIP-01 invariants

NIP-01 defines the on-wire event fields, the `id` derivation serialization, and signature expectations.

Relays respond to `["EVENT", <event>]` with an `["OK", <event_id>, <true|false>, <message>]`, where `<message>` uses a machine-readable prefix followed by `:` and a human-readable message when rejecting, and may be empty when accepting.

## Specification

### 1. Validation pipeline ordering

Implementations MUST validate events in the following order, and MUST stop at the first failure.

1. Parse and basic JSON type check
2. Required fields and basic types
3. Canonical constraints (hex lengths, ranges, integer checks)
4. `id` recomputation and equality check
5. Signature verification
6. Tag structure and standard tag grammar
7. Contextual policy limits (optional, but with a standard mechanism)
8. Apply, store, index, render

Rationale: the pipeline enforces a single "gate" that all feature code depends on, so rendering, indexing, threading, and filtering never touch untrusted structures.

### 2. Parse and basic shape

A raw event MUST be a JSON object.

If parsing fails, or the value is not a JSON object, the event is invalid.

### 3. Required fields and basic types

A raw event MUST contain the following fields, matching the NIP-01 event format.

* `id`, type string
* `pubkey`, type string
* `created_at`, type number
* `kind`, type number
* `tags`, type array
* `content`, type string
* `sig`, type string

If any required field is missing, or any type does not match, the event is invalid.

### 4. Canonical constraints

To reduce differences between implementations and unsafe edge cases, strict validation applies the following canonical constraints.

#### 4.1 Hex fields

The following fields MUST be lowercase hex strings of fixed length:

* `id` MUST be 64 hex characters (32 bytes), lowercase
* `pubkey` MUST be 64 hex characters (32 bytes), lowercase
* `sig` MUST be 128 hex characters (64 bytes), lowercase

These constraints align with how NIP-01 describes these fields on the wire.

If any field fails these constraints, the event is invalid.

#### 4.2 Numeric fields

* `created_at` MUST be an integer representing unix timestamp seconds. NIP-01 defines it as unix timestamp in seconds, and uses it as a number in the serialization.
* `kind` MUST be an integer in the range 0 to 65535 inclusive, as per NIP-01.

If `created_at` or `kind` is not an integer, or if `kind` is out of range, the event is invalid.

Note: this NIP chooses strict integer enforcement to avoid cross-language float and integer conversion differences. NIP-01 serialization uses numbers, but the semantics described for `created_at` and `kind` are integer-based. Very old events (roughly 2021–2022) occasionally used floating-point `created_at` values; strict implementations may reject those, or make this check configurable if backward compatibility is required.

Note: the `kind` range here is the NIP-01 baseline. Some later NIPs use higher kind numbers in practice; strict implementations may choose to accept them or make the allowed range configurable.

### 5. Canonical `id` recomputation

Strict validation MUST recompute `id` exactly as described in NIP-01 and compare it for equality with the provided `id`.

#### 5.1 Serialization input structure

The serialization input MUST be the JSON array:

```
[
  0,
  <pubkey, as a lowercase hex string>,
  <created_at, as a number>,
  <kind, as a number>,
  <tags, as an array of arrays of non-null strings>,
  <content, as a string>
]
```

This is NIP-01's specified structure for deriving `event.id`.

#### 5.2 Tag value constraint for hashing

Because the serialization requires `<tags, as an array of arrays of non-null strings>`, strict validation MUST ensure, before hashing, that:

* `tags` is an array
* every element of `tags` is an array
* every element of each tag array is a string
* no element is null

If these constraints fail, the event is invalid.

#### 5.3 JSON serialization rules

Strict validation MUST follow NIP-01 rules to prevent implementation differences:

* UTF-8 encoding
* no whitespace, line breaks, or unnecessary formatting
* the required escape rules for the `content` field as defined in NIP-01

#### 5.4 Hash check

Compute:

* `payload = utf8(json_serialize(serialization_array))`
* `hash = sha256(payload)`
* `expected_id = lowercase_hex(hash)`

The event is valid only if `expected_id == event.id`.

### 6. Signature verification

After `id` matches, strict validation MUST verify the signature:

* Verify that `sig` is a valid Schnorr signature over the `id`, using `pubkey`, per NIP-01's stated signature scheme.

If signature verification fails, the event is invalid.

### 7. Tag grammar, general rules

After cryptographic validity, strict validation enforces uniform tag structure rules.

#### 7.1 Basic tag rules

* Each tag MUST be an array of one or more strings.
* The first element `tag[0]` is the tag name, and MUST be a non-empty string.
* All elements of a tag MUST be strings, and MUST NOT be null (this is already required for hashing).

If any of these fail, the event is invalid.

#### 7.2 Standard tags

NIP-01 defines standard tags `e`, `p`, and `a` and their conventional structure.

Strict validation enforces the following when these tags appear.

##### `e` tag

If `tag[0] == "e"`:

* `tag[1]` MUST exist and MUST be a 64-character lowercase hex event id
* `tag[2]` MAY exist and is a recommended relay URL string
* `tag[3]` MAY exist and MUST be a 64-character lowercase hex pubkey if present

##### `p` tag

If `tag[0] == "p"`:

* `tag[1]` MUST exist and MUST be a 64-character lowercase hex pubkey
* `tag[2]` MAY exist and is a recommended relay URL string

##### `a` tag

If `tag[0] == "a"`:

* `tag[1]` MUST exist and MUST follow the NIP-01 address format rules for addressable or replaceable events, including the required trailing colon for normal replaceable events as specified.
* `tag[2]` MAY exist and is a recommended relay URL string

If a standard tag fails its grammar, the event is invalid.

Note: This NIP does not attempt to validate the meaning of non-standard tags, only their structural safety.

Non-normative note: the exact `a` tag address format is specified in NIP-33 and related NIPs (for example, NIP-16 and NIP-32). Implementations SHOULD refer to those documents for details.

Non-normative note: other NIPs define structured tags (for example, delegation in NIP-26 or external identities in NIP-39). Implementations MAY add tag-specific validation for those tags. Strict validation here only mandates the `e`/`p`/`a` grammar plus safe structure for all tags.

### 8. Contextual policy limits

Strict validation defines a uniform way to apply local policy limits, without standardizing a single global policy.

Implementations MAY apply limits such as:

* maximum message size in bytes of the WebSocket JSON frame (UTF-8)
* maximum `content` length in Unicode characters (not bytes)
* maximum number of tag arrays
* acceptable `created_at` skew relative to local clock
* minimum proof of work difficulty if required by a relay

NIP-11 defines a standard way for relays to communicate limits such as `max_message_length` (bytes of the WebSocket JSON frame), `max_content_length` (Unicode character count, not bytes), `max_event_tags` (count of tag arrays), `min_pow_difficulty` (as defined in NIP-13), and `created_at_lower_limit`/`created_at_upper_limit` (relay policy limits). Clients implementing this NIP SHOULD apply relay-provided limits consistently when publishing to that relay.

Timestamp sanity windows are policy limits, not part of cryptographic validity. This avoids breaking NIP-59 use cases where timestamps may be manipulated and relays may apply their own limits.

If a contextual limit is violated, the event SHOULD be rejected with a reason that indicates policy, not cryptographic invalidity.

### 9. Applying validated events

After an event passes strict validation, implementations SHOULD treat it as immutable:

* store it keyed by `id`
* if the same `id` is seen again, treat as duplicate and ignore
* build indices and views from the stored canonical structure, not from raw inbound JSON

Relays already commonly communicate duplicate handling using the `OK` response message format, and NIP-01 gives examples such as `duplicate: already have this event`.

## Relay behavior

### Accepting `EVENT`

Relays implementing this NIP SHOULD perform strict validation for every inbound `EVENT`.

* If accepted, respond with `["OK", <event_id>, true, <message>]` where `<message>` MAY be empty.
* If rejected, respond with `["OK", <event_id>, false, <message>]` where `<message>` MUST begin with a machine-readable prefix, followed by `:` and a human-readable message.

Relays that require authentication via NIP-42 MAY use `AUTH` challenges before accepting events. In those cases, `auth-required:` and `restricted:` prefixes may appear in `OK` or `CLOSED` messages to indicate policy or authorization failure, not event-format or cryptographic invalidity. Clients MUST NOT treat these as `invalid:` failures.

### Recommended error prefixes for strict validation

This NIP recommends using the existing NIP-01 error pattern and the `invalid:` prefix family only for NIP-01 structural or cryptographic violations. All other rejections, including NIP-42 authentication or authorization failures, MUST use non-`invalid` policy-style prefixes.

Use:

* `invalid: parse` for non-JSON or non-object
* `invalid: missing-field <field>`
* `invalid: type <field>`
* `invalid: hex <field>`
* `invalid: range kind`
* `invalid: id-mismatch`
* `invalid: sig`
* `invalid: tags-structure`
* `invalid: tag-e`
* `invalid: tag-p`
* `invalid: tag-a`

Example:

* `["OK", "<id>", false, "invalid: id-mismatch"]`
* `["OK", "<id>", false, "invalid: tag-e"]`

Policy-related failures SHOULD use non-`invalid` prefixes, for example:

* `rate-limited: ...`
* `restricted: ...`
* `auth-required: ...`
* `pow: ...`

These prefixes and the overall format are aligned with NIP-01 examples.

## Client behavior

Clients implementing this NIP SHOULD:

1. Validate before signing and publishing
2. Validate after receiving from relays, before storing or rendering
3. Ensure feature code never consumes raw events

Clients SHOULD apply relay limits when publishing, based on NIP-11 relay information, to reduce rejected publishes and inconsistent behavior across relays.

## Compatibility

* This NIP is compatible with the NIP-01 on-wire event format and message flow.
* This NIP may cause some older or malformed events to be rejected by strict implementations, especially events with non-integer `created_at` or malformed tags. This is intentional for strict mode.

Clients that want maximum backwards compatibility MAY support a "base mode" that only enforces NIP-01 minimums, and a "strict mode" that enforces this NIP.

## Security considerations

Strict validation reduces risk by:

* preventing malformed tag structures from reaching indexing and rendering
* preventing signature bypass through type confusion
* ensuring `id` and signature checks happen before any feature logic
* preventing divergent `id` calculations across implementations by forcing uniform serialization rules

This NIP does not solve spam or abuse by itself, but it provides a safer base for rate limiting and policy enforcement.

## Reference algorithm (pseudocode)

```
function validate_strict(event, context):
  # 1. parse and shape
  assert is_object(event)

  # 2. required fields and basic types
  require_fields(event, ["id","pubkey","created_at","kind","tags","content","sig"])
  assert is_string(event.id)
  assert is_string(event.pubkey)
  assert is_number(event.created_at)
  assert is_number(event.kind)
  assert is_array(event.tags)
  assert is_string(event.content)
  assert is_string(event.sig)

  # 3. canonical constraints
  assert is_lower_hex(event.id, 64)
  assert is_lower_hex(event.pubkey, 64)
  assert is_lower_hex(event.sig, 128)
  assert is_integer(event.created_at)
  assert is_integer(event.kind)
  assert 0 <= event.kind <= 65535
  # optional: allow legacy float created_at in compatibility mode

  # 4. tags hashing constraint
  for tag in event.tags:
    assert is_array(tag)
    assert len(tag) >= 1
    for x in tag:
      assert is_string(x) and x is not null
    assert tag[0] != ""

  # 5. recompute id per NIP-01
  ser = [0, event.pubkey, event.created_at, event.kind, event.tags, event.content]
  payload = utf8(json_serialize_no_whitespace_with_nip01_escapes(ser))
  expected_id = sha256_hex_lower(payload)
  assert expected_id == event.id

  # 6. verify sig per NIP-01
  assert schnorr_verify(pubkey=event.pubkey, msg=event.id, sig=event.sig)

  # 7. standard tag grammar
  for tag in event.tags:
    assert tag[0] != ""
    if tag[0] == "e":
      assert len(tag) >= 2
      assert is_lower_hex(tag[1], 64)
      if len(tag) >= 4:
        assert is_lower_hex(tag[3], 64)
    if tag[0] == "p":
      assert len(tag) >= 2
      assert is_lower_hex(tag[1], 64)
    if tag[0] == "a":
      assert len(tag) >= 2
      # includes trailing colon for normal replaceable events
      assert matches_nip01_a_format(tag[1])

  # 8. contextual policy limits (optional)
  if context has limits:
    assert passes_limits(event, context.limits)

  return VALIDATED_EVENT(event)
```
