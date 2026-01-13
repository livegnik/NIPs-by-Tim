## Table of contents

### Validation and State Integrity (XX1-XX6)
- [XX1. Validation Framework for NIP-01 Events](#xx1-validation-framework-for-nip-01-events)
- [XX2. Relay Policy Declaration, Rejection Codes, and Backpressure](#xx2-relay-policy-declaration-rejection-codes-and-backpressure)
- [XX3. Relay Ingress Pipeline Standardization](#xx3-relay-ingress-pipeline-standardization)
- [XX4. Deterministic Replaceable Resolution](#xx4-deterministic-replaceable-resolution)
- [XX5. Idempotent Storage Semantics and Duplicate Handling](#xx5-idempotent-storage-semantics-and-duplicate-handling)
- [XX6. Deletion, Tombstones, and Query Visibility Rules](#xx6-deletion-tombstones-and-query-visibility-rules)

### Querying, Fetch, and Discovery (XX7-XX9)
- [XX7. Cursor Pagination and Stable Query Continuations](#xx7-cursor-pagination-and-stable-query-continuations)
- [XX8. Trust-Scoped Fetch Defaults and Relay List Discipline](#xx8-trust-scoped-fetch-defaults-and-relay-list-discipline)
- [XX9. Multi-Hop Discovery and Scoped Relay Assist](#xx9-multi-hop-discovery-and-scoped-relay-assist)

### Safety, Auth, and Privacy (X10-X14)
- [X10. Admission Control and Unified Anti-Abuse Profile](#x10-admission-control-and-unified-anti-abuse-profile)
- [X11. Identity Safety: Scoped Keys, Delegation, Remote Signing, Continuity](#x11-identity-safety-scoped-keys-delegation-remote-signing-continuity)
- [X12. Relay Authentication Profile and Capability Grants](#x12-relay-authentication-profile-and-capability-grants)
- [X13. Privacy Baseline: Encryption Profiles per Use Case](#x13-privacy-baseline-encryption-profiles-per-use-case)
- [X14. Privacy Baseline: Mandatory Wrapping for Sensitive Operations](#x14-privacy-baseline-mandatory-wrapping-for-sensitive-operations)

### Graph, Reputation, and Namespaces (X15-X18)
- [X15. Relationship Events as First-Class Graph Edges](#x15-relationship-events-as-first-class-graph-edges)
- [X16. Scoped Ratings and Reputation Signals with Distance](#x16-scoped-ratings-and-reputation-signals-with-distance)
- [X17. App Namespace Tag and Collision-Resistant Schemas](#x17-app-namespace-tag-and-collision-resistant-schemas)
- [X18. Deterministic Client Journal and Rebuild Semantics](#x18-deterministic-client-journal-and-rebuild-semantics)

### Relay Topology and Storage (X19-X24)
- [X19. Relay-to-Relay Peering and Replication](#x19-relay-to-relay-peering-and-replication)
- [X20. Relay Retention Contracts and Storage Roles](#x20-relay-retention-contracts-and-storage-roles)
- [X21. Mesh Transport Topology Gossip and Route Hints](#x21-mesh-transport-topology-gossip-and-route-hints)
- [X22. Content Addressing and Chunked Large Object Transport](#x22-content-addressing-and-chunked-large-object-transport)
- [X23. Proof-Carrying Attestations Container](#x23-proof-carrying-attestations-container)
- [X24. Atomic Operation Bundles and Dependency Manifests](#x24-atomic-operation-bundles-and-dependency-manifests)

### Profiles, Policies, and Client Behavior (X25-X33)
- [X25. Event Type Profiles for Well-Known Kinds](#x25-event-type-profiles-for-well-known-kinds)
- [X26. Semantic Failure Taxonomy and Prefix Discipline](#x26-semantic-failure-taxonomy-and-prefix-discipline)
- [X27. Standard Client Retry, Queue, and Backoff Rules](#x27-standard-client-retry-queue-and-backoff-rules)
- [X28. Subscription Hygiene and Resource Budgets](#x28-subscription-hygiene-and-resource-budgets)
- [X29. Relay Index Capability Advertisement](#x29-relay-index-capability-advertisement)
- [X30. Standardized Event Receipts and Delivery Proof Hints](#x30-standardized-event-receipts-and-delivery-proof-hints)
- [X31. Network Partition and Offline Posting Semantics](#x31-network-partition-and-offline-posting-semantics)
- [X32. Relay Federation Guardrails for Privacy and Metadata](#x32-relay-federation-guardrails-for-privacy-and-metadata)
- [X33. Relay Accountability, Transparency, and Operator Signatures](#x33-relay-accountability-transparency-and-operator-signatures)

### Moderation and Communities (X34-X37)
- [X34. Moderation Decision Objects and Multi-Signature Governance](#x34-moderation-decision-objects-and-multi-signature-governance)
- [X35. Community Membership Objects and Access Policies](#x35-community-membership-objects-and-access-policies)
- [X36. Namespace Governance and Policy Layers](#x36-namespace-governance-and-policy-layers)
- [X37. Relay Quality Signals and Client Relay Selection Strategy](#x37-relay-quality-signals-and-client-relay-selection-strategy)

### Consistency and User Experience (X38-X43)
- [X38. Deterministic Merge Rules for Multi-Relay Views](#x38-deterministic-merge-rules-for-multi-relay-views)
- [X39. Standard Thread Reconstruction and Reply Semantics](#x39-standard-thread-reconstruction-and-reply-semantics)
- [X40. Deterministic Notification Semantics](#x40-deterministic-notification-semantics)
- [X41. Explicit User Consent and Data Minimization Hints](#x41-explicit-user-consent-and-data-minimization-hints)
- [X42. Standard Cross-Client Settings Synchronization](#x42-standard-cross-client-settings-synchronization)
- [X43. Standardized Mute, Block, and Label Objects](#x43-standardized-mute-block-and-label-objects)

### Search, Integrity, and Trust Signals (X44-X48)
- [X44. Search and Discovery Protocol Baseline](#x44-search-and-discovery-protocol-baseline)
- [X45. Secure Link and Media Integrity Signaling](#x45-secure-link-and-media-integrity-signaling)
- [X46. Device and Client Attestation for Risk Reduction](#x46-device-and-client-attestation-for-risk-reduction)
- [X47. Standard Abuse Reporting and Evidence Bundles](#x47-standard-abuse-reporting-and-evidence-bundles)
- [X48. Verified Service Announcements and Directory Objects](#x48-verified-service-announcements-and-directory-objects)

### Economics and Efficiency (X49-X53)
- [X49. Economic Signaling for Relay Sustainability](#x49-economic-signaling-for-relay-sustainability)
- [X50. Interoperable Event Compression and Bandwidth Reduction](#x50-interoperable-event-compression-and-bandwidth-reduction)
- [X51. Interoperable Payment Intents and Settlement Objects](#x51-interoperable-payment-intents-and-settlement-objects)
- [X52. Commerce Objects for Goods, Services, and Subscriptions](#x52-commerce-objects-for-goods-services-and-subscriptions)
- [X53. Standard Receipt Objects for Actions and State Changes](#x53-standard-receipt-objects-for-actions-and-state-changes)

### Governance and Lifecycle (X54-X60)
- [X54. Formal Versioning, Migration, and Deprecation for NIPs](#x54-formal-versioning-migration-and-deprecation-for-nips)
- [X55. Profile and Schema Migration Objects](#x55-profile-and-schema-migration-objects)
- [X56. Formal Test Vectors and Conformance Suites](#x56-formal-test-vectors-and-conformance-suites)
- [X57. Graceful Degradation and Partial Support Signaling](#x57-graceful-degradation-and-partial-support-signaling)
- [X58. Formal NIP Lifecycle and Governance Process](#x58-formal-nip-lifecycle-and-governance-process)
- [X59. Cross-Protocol Bridging and Import Semantics](#x59-cross-protocol-bridging-and-import-semantics)
- [X60. Long-Term Archival and Snapshot Semantics](#x60-long-term-archival-and-snapshot-semantics)

### Identity, Automation, and Policy (X61-X63)
- [X61. Social Recovery and Guardian-Based Identity Restoration](#x61-social-recovery-and-guardian-based-identity-restoration)
- [X62. Automation Disclosure and Bot Identity Contracts](#x62-automation-disclosure-and-bot-identity-contracts)
- [X63. Legal, Policy, and Compliance Notice Objects](#x63-legal-policy-and-compliance-notice-objects)

### Portability and Accessibility (X64-X66)
- [X64. Deterministic Export and Portability Bundles](#x64-deterministic-export-and-portability-bundles)
- [X65. Accessibility Metadata for Assistive Rendering](#x65-accessibility-metadata-for-assistive-rendering)
- [X66. Locale and Time Context Signaling](#x66-locale-and-time-context-signaling)

### Rendering and Ranking (X67-X68)
- [X67. Deterministic Rendering Hints and Layout Semantics](#x67-deterministic-rendering-hints-and-layout-semantics)
- [X68. Feed Ranking Signal Objects and Explainable Relevance](#x68-feed-ranking-signal-objects-and-explainable-relevance)

### Ephemeral and Rights (X69-X70)
- [X69. Ephemeral Content and Expiration Semantics](#x69-ephemeral-content-and-expiration-semantics)
- [X70. Content Licensing and Usage Rights Objects](#x70-content-licensing-and-usage-rights-objects)

### Credentials and Client Safety (X71-X75)
- [X71. Anonymous Credential Presentation and Selective Disclosure](#x71-anonymous-credential-presentation-and-selective-disclosure)
- [X72. Proof-of-Personhood and Sybil-Resistance Hooks](#x72-proof-of-personhood-and-sybil-resistance-hooks)
- [X73. Cross-Device State Sync and Conflict Resolution](#x73-cross-device-state-sync-and-conflict-resolution)
- [X74. Client Plugin Sandboxing and Permission Scopes](#x74-client-plugin-sandboxing-and-permission-scopes)
- [X75. Emergency Network Mode and Graceful Degradation Signaling](#x75-emergency-network-mode-and-graceful-degradation-signaling)

# XX1. Validation Framework for NIP-01 Events

## How it’s related to 2WAY

2WAY is built around the idea that raw inbound data is never “application state” until it has passed a strict, consistent pipeline. The system boundary is enforced by shared managers and engines so that every consumer sees the same canonical shape and meaning. That is exactly the role this NIP plays for Nostr: it formalizes the “Incoming Engine boundary” concept, where parsing, canonicalization, and acceptance are centralized and deterministic, rather than scattered across feature code paths.

## The NIP idea

Define a mandatory, ordered validation pipeline for all NIP-01 events, applied identically by clients and relays. The pipeline must specify exact stages, required checks, and hard failure outcomes. At minimum: JSON parse, type checks for required fields, tag structure checks, canonical serialization, id recomputation, signature verification, and basic invariants such as non-null fields, correct types, and bounded sizes when the relay advertises them. The NIP must define when an event becomes “valid”, and it must require that once an event is considered valid, it is immutable and treated as a stable operation input. The NIP must also define how implementations should report failures in a structured way, without changing the event format.

## What this NIP solves in general

Nostr has a recurring class of bugs where “the protocol is simple” but implementations disagree on what “valid” means in practice. Some clients accept malformed tags and compensate later. Some relays enforce hidden constraints without describing them. Some code paths verify signatures early, others late. That inconsistency forces every app feature, threading, indexing, rendering, notifications, to become defensive code. This NIP stops that leak. When validation is strict and ordered, the ecosystem converges on one definition of “valid input”, which reduces crashes, reduces duplicate handling inconsistencies, reduces weird replay behavior, and makes every downstream algorithm simpler because it can assume inputs are well-formed and verified.

## Practical example of problems

A client receives an event where `tags` is present but contains an element that is not an array of strings, for example a nested object or a null. One client ignores it and continues. Another client tries to parse an `e` or `p` tag and fails a cast, breaking thread reconstruction. A relay might accept it and store it, then other clients repeatedly trip on it forever. Or the opposite: one relay rejects it but another accepts it, so users see inconsistent timelines depending on relay choice. With XX1, all implementations reject it at the same stage with the same meaning. The event never becomes storable or renderable, and the bug does not propagate.

## What other NIPs this NIP relies on

* NIP-01 (event format, serialization and signature rules).
* XX2 (structured rejection reporting) if you want uniform failure codes, but XX1 can exist without it.

---

# XX2. Relay Policy Declaration, Rejection Codes, and Backpressure

## How it’s related to 2WAY

2WAY explicitly separates “acceptance gates” from “application state flow”. The Bastion Engine and DoS Guard gate admission, and the system logs failures as first-class outcomes instead of silent drops. That same philosophy applies to Nostr relays. Without structured reasons and backpressure, clients blindly retry, relays silently fail, and the network becomes unstable under load. XX2 is the Nostr equivalent of making relay behavior observable and machine-actionable, instead of relying on tribal knowledge.

## The NIP idea

Extend relay metadata and relay responses so that relays can declare enforceable limits and clients can respond responsibly. This NIP standardizes: a machine-readable list of limits (max event size, max tag count, timestamp windows, supported auth modes, supported validation profiles), structured rejection codes for writes and subscriptions, and explicit backpressure semantics such as “retry-after” hints or temporary refusal categories. The NIP must define stable categories like invalid, unauthorized, policy-rejected, rate-limited, overloaded, and temporarily unavailable. It must define what clients should do for each category, including whether to retry, how long to back off, and how to surface it to users. It must not depend on proprietary strings.

## What this NIP solves in general

At scale, the biggest operational problem is not cryptography, it is overload behavior and inconsistent policy enforcement. When relays fail silently, clients retry aggressively. When relays return vague reasons, clients guess. When policy is “out of band”, users blame clients for missing posts. XX2 makes relays predictable and makes clients polite by default. It reduces accidental self-DoS from aggressive reconnection. It reduces fragmentation because limits are visible. It also enables incremental upgrades. A relay can tighten policy while still telling clients exactly what changed, which avoids breaking older clients in confusing ways.

## Practical example of problems

A relay is under heavy load. Today it might close sockets, drop events, or respond with an unstructured “OK false” message. Clients interpret this as transient network failure and retry in a tight loop. The relay collapses harder and the failure spreads. Another relay might reject because the event is slightly too large, but the client does not know the max size, so it keeps trying, wasting bandwidth and battery. With XX2, the relay can say “overloaded, retry-after 30 seconds” and the client backs off automatically. Or it can say “policy, event too large, max bytes X”, so the client can truncate, compress, or warn the user.

## What other NIPs this NIP relies on

* NIP-11 (relay information document concept).
* XX1 (strict validation) improves consistency, but XX2 can exist without XX1.
* NIP-42 if you want standard auth-related rejections to be interoperable.

---

# XX3. Relay Ingress Pipeline Standardization

## How it’s related to 2WAY

2WAY is explicit about staged processing. Traffic hits a defensive gate, then goes through filtering, queuing, routing, and only then becomes state changes. That is how you stop “random feature code” from becoming a security boundary. Nostr relays currently behave as if every relay has its own hidden pipeline ordering, and clients suffer because they cannot predict what will happen first. XX3 makes the relay’s ingestion steps explicit, similar to how 2WAY’s engines create a predictable boundary between network input and state mutation.

## The NIP idea

Define a normative relay ingress pipeline, including the required order of major steps and the permissible variance points. For example: parse, basic structural validation, authentication check if required, rate limiting and admission control, authorization checks, full validation, storage, indexing, and fanout to subscribers. The NIP must define which failure types can occur at each step, what the relay must return, and whether the relay may short-circuit earlier. It must also define what data the relay may persist before full validation, ideally none except temporary buffers. The relay must be able to declare this pipeline profile in its metadata so clients can debug mismatches and implement consistent fallback logic.

## What this NIP solves in general

Many “interop” bugs are not about event format, they are about operational ordering. One relay may rate-limit before validation and reject quickly. Another may validate first and then rate-limit, causing different rejection semantics, different load patterns, and different attack surfaces. Some relays might store then index later, causing temporary query inconsistencies. XX3 reduces this chaos. It gives clients a stable mental model, it gives relay operators a reference design, and it makes debugging possible. Most importantly, it prevents security-sensitive checks from accidentally being bypassed by alternate code paths, because the pipeline is a contract rather than a tradition.

## Practical example of problems

Two relays both claim to support the same NIPs. A client sends a publish. Relay A checks rate limits first and returns a structured rate-limit rejection, so the client queues the event locally and retries later. Relay B validates first and spends CPU verifying signatures and parsing tags, then rate-limits, then drops. Under abuse, Relay B burns resources and becomes unstable faster. Users then see inconsistent behavior: sometimes posts appear quickly, sometimes they never appear, depending on relay selection and load. With XX3, both relays follow the same ingestion ordering. The client sees consistent rejection reasons, and relay operators can scale defenses without inventing a bespoke pipeline.

## What other NIPs this NIP relies on

* XX2 (structured rejection categories and relay policy declaration).
* XX1 (validation framework) if the relay declares it uses strict validation, but XX3 can exist with looser validation if declared.

---

# XX4. Deterministic Replaceable Resolution

## How it’s related to 2WAY

2WAY’s State Engine concept exists to ensure consistent outcomes regardless of ordering, duplication, or partitioning. That is the central “correctness at scale” principle. Replaceable and parameterized replaceable events are exactly where Nostr turns from a raw feed into state, profiles, lists, settings, and app configs. If clients pick different winners, state diverges. XX4 is the direct translation of 2WAY’s “deterministic convergence” idea applied to the specific Nostr state surfaces that already exist.

## The NIP idea

Define normative rules for selecting the current value among competing replaceable and parameterized replaceable events. Specify exact tie-breakers. For example: primary order by `created_at`, then by event id as a deterministic tiebreak, and define how to handle invalid timestamps. Define the canonical “coordinate” for parameterized replaceable events and ensure all implementations compute it the same way. Define whether relays should store all historical versions, whether they should serve only the winning version by default, and how clients should interpret multiple versions in a feed. Define behavior under clock skew, including recommended timestamp windows and what happens when events are outside those windows.

## What this NIP solves in general

State drift is toxic because it breaks identity and UX. If two clients show different profile metadata, different relay lists, or different app settings for the same pubkey, users stop trusting the network. This drift happens because arrival order differs across relays and because tie cases occur when updates are close in time or devices have skewed clocks. XX4 makes the final state deterministic and the same everywhere. It also makes relays more predictable: the relay can serve a consistent “current” value and optionally keep history. That reduces client complexity and makes caching safe, which reduces load.

## Practical example of problems

A user updates their profile on a phone and on a laptop within seconds. Phone clock is slightly ahead. Relay X receives the laptop update first, Relay Y receives the phone update first. Client A reads from Relay X, Client B reads from Relay Y. The user sees different bios and avatars across clients, and followers see inconsistent identity metadata. With XX4, both clients pick the same winning event based on deterministic rules, not “first seen”. If the phone timestamp is outside the acceptable window, it is handled consistently. This also avoids a common abuse pattern where spammers post future-dated replaceable events to lock in a “winning” state.

## What other NIPs this NIP relies on

* NIP-01 (replaceable event concept and id rules).
* XX1 (strict validation) strengthens correctness but is not strictly required.
* XX2 if using relay-declared timestamp policy windows.

---

# XX5. Idempotent Storage Semantics and Duplicate Handling

## How it’s related to 2WAY

2WAY assumes duplicates are normal because P2P sync and multi-hop routing produce repeated deliveries. The design goal is that applying the same operation twice never corrupts state. That is why 2WAY emphasizes canonical object identifiers, logging, and apply-once semantics at the boundary. Nostr at scale has the same reality. Events will arrive multiple times from multiple relays, multiple paths, and after reconnection. XX5 is the Nostr version of 2WAY’s “replay is not a bug, but it must be harmless” discipline.

## The NIP idea

Define idempotent storage behavior for both relays and clients. If an event id already exists, storing it again must be a no-op. If a replaceable event arrives that loses by deterministic rules, it may be stored for history or discarded, but it must not overwrite the winner. If deletions arrive before the target event, behavior must be consistent and defined, for example storing a tombstone that suppresses later rendering. Define how “seen” state and notifications should behave under duplicates, including that duplicates must not generate repeated notifications. Define “out of order arrival” expectations and mandate that implementations must not assume causal arrival.

## What this NIP solves in general

Without idempotence, every network optimization creates application bugs. Mesh transports, relay replication, retry logic, and multi-relay reading all increase duplicates. If duplicates create repeated notifications, repeated UI items, inflated counters, or repeated database writes, clients become slow and unusable. Relays waste resources and become easier to DoS. XX5 makes duplicates boring. That directly improves scalability because you can safely increase redundancy, replication, and aggressive fetching without breaking user experience. It also simplifies code: when storage is idempotent by contract, most “dedupe logic” collapses into checking primary keys.

## Practical example of problems

A client subscribes to a feed on three relays for redundancy. Each relay sends overlapping sets of events. The client sees duplicates and sends multiple notifications for the same mention. It also writes duplicates into its database because it keys by “arrival” rather than by event id. Over time, the local store bloats, queries get slow, and the UI becomes inconsistent. Or a relay replicates from a peer relay and accidentally re-inserts events, triggering re-indexing storms. With XX5, event id uniqueness is a hard rule. Both relay and client treat duplicates as no-ops. Notifications and indexes are updated once, and redundancy no longer breaks UX.

## What other NIPs this NIP relies on

* NIP-01 (event id as canonical dedupe key).
* XX4 (deterministic replaceable resolution) for consistent overwrite behavior.
* XX6 (deletion and tombstones) for out-of-order delete interactions.

---

# XX6. Deletion, Tombstones, and Query Visibility Rules

## How it’s related to 2WAY

2WAY treats object lifecycle and visibility as explicit. The design includes the idea that objects can be created, updated, deleted, and also down-voted or hidden, and that visibility is part of state semantics rather than an afterthought. That approach exists because distributed systems cannot rely on “everyone forgot it”. Nostr deletions suffer from the same reality. XX6 applies 2WAY’s explicit lifecycle and visibility thinking to Nostr: deletion becomes a first-class state outcome with defined query and render behavior, not a best-effort suggestion.

## The NIP idea

Tighten delete semantics by defining exactly what relays and clients must do when they accept a delete event. Define “tombstone” representation and whether it is stored as metadata, as a synthetic record, or as a suppressed id set. Define query behavior: whether deleted events are omitted by default, how clients learn they were deleted, and whether tombstones can be queried explicitly for audit. Define out-of-order behavior: what happens if a delete arrives before the target event, and whether later arrival of the target should be suppressed. Define how deletes interact with replaceable events and whether deletes can target state coordinates. Define retention expectations around tombstones so deletes do not silently reappear due to replication.

## What this NIP solves in general

Right now, deletion is inconsistent in practice. Some relays delete, some ignore, some partially delete but still serve through certain queries. Some clients treat deleted events as gone, others show ghost placeholders, others re-render after a restart because local caches still contain them. At scale, this becomes a trust problem. Users do not care about philosophical permanence, they care about predictable behavior. XX6 makes deletion predictable. It reduces ghost content, reduces harassment persistence through relay quirks, and improves performance because deleted content can be filtered efficiently if tombstones are handled consistently.

## Practical example of problems

A user posts a private mistake, then deletes it. Relay A honors the delete and stops serving it. Relay B keeps it because it does not implement deletion fully. Client X reads Relay A and the post seems gone. Client Y reads Relay B and it still appears, and other users can quote it forever. Or a delete arrives while a client is offline, and when the client reconnects it pulls older content that includes the now-deleted event, and it renders it because it never saw the delete, or it processed the delete but did not persist a tombstone. With XX6, relays and clients implement a consistent tombstone rule. Deleted content stays suppressed even under re-sync and replication.

## What other NIPs this NIP relies on

* NIP-09 (deletion concept) as the base.
* XX1 (validation) to prevent malformed deletes and spoofed targets.
* XX5 (idempotent semantics) for out-of-order and replay-safe deletion handling.

---

# XX7. Cursor Pagination and Stable Query Continuations

## How it’s related to 2WAY

2WAY’s model is “ordered operations and stable replay”. When you query or sync beyond immediate peers, you need stable continuation so that results do not shift unpredictably while the network changes. That is part of why 2WAY uses structured state engines and controlled propagation paths, rather than ad hoc fetches. Cursor pagination is the Nostr-side equivalent: it turns “scrolling a firehose” into a stable retrieval contract. It reduces repeated queries, reduces missing items, and makes client caches reliable. This aligns with 2WAY’s emphasis on deterministic rebuild and predictable state access patterns.

## The NIP idea

Define a relay-supported cursor system for subscriptions and historical queries. The cursor must be opaque, relay-issued, and stable for a bounded time. It must encode an ordering key that is deterministic, for example created_at plus id tiebreak, so that pagination does not repeat or skip items even as new events arrive. Define how clients request “next page” and how relays handle cursor expiration. Define compatibility behavior: clients that do not support cursors can continue using existing since and until filters, but cursor-aware clients should prefer cursors for large feeds. Define how multiple relays interact: clients may maintain per-relay cursors and merge results locally, or a relay may offer merged cursors if it does replication.

## What this NIP solves in general

At scale, “infinite scroll” becomes expensive and buggy because result sets are unstable. Clients either re-query broad ranges, causing repeated bandwidth and duplicates, or they use timestamps and miss items due to ties and clock skew. Relays can reorder based on internal indexing and deliver overlapping windows. Cursor pagination makes retrieval stable. It reduces load, reduces duplicate deliveries, and makes offline clients practical because they can resume from a checkpoint. It also improves UX because scrolling does not jump or repeat randomly. This is high impact because it addresses the core read path that every user hits constantly.

## Practical example of problems

A client loads the last 100 posts from followed users across multiple relays. It uses `until` based on the oldest event timestamp. Several events share the same timestamp, and each relay orders them differently. On the next page, the client either repeats some events or skips some. Users see gaps in threads and missing replies. Under heavy posting, the set shifts while the user scrolls, so the client may refetch overlapping windows repeatedly. With XX7, the relay gives a cursor after the first page. The next request uses that cursor, and the relay returns the next segment in a stable order. No repeats, no gaps, less bandwidth, less CPU.

## What other NIPs this NIP relies on

* XX4 (deterministic ordering rules) if you want a shared ordering basis.
* XX5 (idempotent handling) for safe multi-relay merging of paginated results.
* NIP-01 filters as the baseline query mechanism.

---

# XX8. Trust-Scoped Fetch Defaults and Relay List Discipline

## How it’s related to 2WAY

2WAY explicitly rejects global broadcast. Servers communicate only with known peers defined in a Server Graph, and queries beyond immediate peers are bounded by degree-of-separation and trust paths. That is a direct architectural choice to reduce metadata leakage and to avoid network-wide disruption.  Nostr today often behaves like the opposite, clients spray requests to large public relays. XX8 applies the 2WAY principle as a client behavior contract: fetch is scoped by default to explicit relay lists and social graph adjacency, not the global firehose.

## The NIP idea

Define normative client behavior for selecting relays for reads and writes, using relay list metadata as the primary signal. Specify default sets: write relays, read relays, and mention relays. Define fallback order and caching rules so clients do not constantly churn relay sets. Define social-graph driven discovery rules: for example, when fetching a followed user’s content, prefer that user’s declared relays first, then the viewer’s own relays, then optional fallback relays. Define strict limits on how many “public fallback relays” a client should query by default. Define a compatibility mode so older clients can still query broadly, but modern clients should prefer scoped strategies. This is a NIP about default behavior, not new cryptography.

## What this NIP solves in general

Global fanout is a scaling killer. It amplifies spam, increases bandwidth cost, and makes users dependent on a small set of “mega relays”. It also leaks metadata because a client that queries everywhere broadcasts its interests. Trust-scoped defaults reduce both cost and leakage. They also improve reliability because content retrieval becomes aligned with where the author actually writes. Relay list discipline reduces missing replies and missing mentions, because clients stop guessing where to publish. This is high impact because it addresses the core scaling pattern: how many relays each client hits per refresh. Reducing that by an order of magnitude is a real network-level win.

## Practical example of problems

A user posts on two relays. Their followers use clients that query ten random popular relays, hoping to find content. Some followers never see the post because those ten relays do not include the author’s write relays. Meanwhile, the client burns bandwidth querying relays that will never have the content. On the spam side, a spammer posts to a popular relay, and because clients query popular relays by default, the spam spreads everywhere. With XX8, followers fetch an author’s posts primarily from the author’s declared relays, and clients keep a disciplined fallback. That increases post visibility, reduces wasted traffic, and reduces spam amplification by default.

## What other NIPs this NIP relies on

* NIP-65 (relay list metadata concept).
* XX7 (pagination) benefits strongly, but not required.
* XX2 (relay policy declaration) helps clients choose reliable relays.

---

# XX9. Multi-Hop Discovery and Scoped Relay Assist

## How it’s related to 2WAY

2WAY allows a server to query beyond its immediate peers through multi-hop relay paths defined by trust relationships, and it explicitly bounds how far those queries can propagate using degree-of-separation.  That creates a middle ground between isolation and global broadcast. Nostr is missing that middle ground. Either you query global relays or you do not. XX9 imports the same concept in Nostr terms: discovery can be assisted, but bounded, privacy-aware, and explicitly scoped, rather than turning every relay into a global index.

## The NIP idea

Define a scoped discovery mechanism where a client can request help finding events, profiles, or relay hints through a bounded chain of relays. The chain can be explicit or relay-selected, but the request must include hop limits and privacy constraints. The relay assist should return either events, relay pointers, or proofs that a search was attempted within a scope. Define how requests are authenticated if needed, and define how relays prevent abuse, for example limiting scoped discovery queries or requiring capability tokens. Define how clients should use assist results, for example adding relays temporarily to a read set for a single fetch, not permanently. Define that assist must not become a global crawling API.

## What this NIP solves in general

The biggest discovery problem in Nostr is “I know a person or event exists but I cannot find it without asking huge relays”. That pushes everyone toward central indexes. XX9 gives a scalable alternative. It preserves decentralization because discovery is bounded and optional. It preserves privacy better than global crawling because the search is limited in scope. It improves reliability because clients have a structured way to expand their view when needed, without permanently switching to mega relays. This becomes high impact once you combine it with trust-scoped defaults. Clients mostly stay local, and only escalate when necessary, and even then in a controlled way.

## Practical example of problems

You are following a person who changes their relay list. Your client misses their posts because you do not know the new write relays. Today the usual fix is “add a big relay”. That is centralization. With XX9, your client asks one of your relays for scoped discovery, for example “within two hops, find recent events for pubkey X or relay hints for pubkey X”. The assist returns a relay pointer that is already known in your social graph or trust set. The client then fetches the author’s metadata from that relay and updates its relay set. You recovered discovery without joining the global firehose.

## What other NIPs this NIP relies on

* XX8 (trust-scoped relay discipline) so assist is an exception rather than default behavior.
* XX2 or X10 for abuse control, depending on whether assist is rate-limited or capability-gated.

---

# X10. Admission Control and Unified Anti-Abuse Profile

## How it’s related to 2WAY

2WAY includes explicit DoS resistance, including client puzzles at the Bastion boundary, and it treats influence limits as a protocol-level concern rather than app-specific hacks. In your networking description, a connection attempt hits a challenge gate before deeper interaction.  That is the model Nostr relays need at scale: cheap reads, but controlled writes, and predictable admission. X10 translates that into Nostr by standardizing session-level puzzles, rate-limit policy composition, and how auth and PoW can be combined without fragmentation.

## The NIP idea

Define a unified relay anti-abuse profile that relays can declare and clients can implement automatically. The profile can include: session-level puzzles for admission, per-event PoW requirements when desired, authentication requirements, per-ip or per-pubkey rate limits, and usage tiers. The NIP must define how a relay challenges a client, what the challenge format is, how difficulty is expressed, and how long a solved challenge remains valid. It must define how these controls compose. For example, a relay may require auth for writes, plus a low puzzle for new connections, plus higher puzzle for bursts, and optionally per-event PoW for anonymous posting. The NIP must define compatibility behavior so older clients can still read.

## What this NIP solves in general

Nostr relays fail under abuse before they fail under popularity. Today defenses are fragmented and inconsistent, causing clients to break unpredictably and encouraging users to centralize around a few heavily defended relays. A unified profile makes defenses interoperable. It reduces bot floods by raising marginal cost. It reduces accidental client-driven DoS by making rate limits visible and by defining backoff rules. It also enables relays to offer stable service tiers, including public, private, and paid access, without each relay inventing a custom protocol. This is high impact because it addresses the hard operational reality: if relays cannot defend themselves cheaply, the network centralizes.

## Practical example of problems

A spam botnet opens thousands of websocket connections and submits events rapidly. Many relays accept connections cheaply and only rate-limit after expensive signature verification, so they burn CPU and die. Clients then reconnect to other relays and amplify load. With X10, a relay can require a lightweight session puzzle at connection time for write-capable sessions. Bots now pay compute per session. The relay can also increase puzzle difficulty dynamically for suspicious patterns. Legitimate clients solve once and continue. If the relay also supports auth, authenticated users can get easier admission. The result is that relay stability improves without turning every post into heavy PoW.

## What other NIPs this NIP relies on

* XX2 (structured rejection and backpressure).
* NIP-13 if per-event PoW is used, but X10 can exist with puzzles only.
* NIP-42 if authentication is part of the profile.

---

# X11. Identity Safety: Scoped Keys, Delegation, Remote Signing, Continuity

## How it’s related to 2WAY

2WAY treats identity as foundational infrastructure, not a single fragile key stuck inside random clients. It assumes operational safety: different roles, different credentials, revocation, and continuity over time. The system is designed so that protected keys do not have to live inside every component that acts on behalf of a user. That maps directly onto Nostr’s biggest adoption risk: key compromise. X11 translates the 2WAY view into a coherent identity safety package for Nostr, combining role-scoped keys, delegation, remote signing, and compromise recovery chains into one standard model rather than scattered “optional features”.

## The NIP idea

Define a unified identity safety model with four parts. First, scoped keys: derive or designate distinct keys for posting, DMs, moderation, automation, and device sessions, with clear recommended constraints and client UX. Second, delegated session keys: a standardized way to grant limited rights for limited time, including explicit scope, expiry, revocation hints, and replay safety. Third, remote signing baseline: define minimum interoperability expectations for remote signers so clients can avoid holding primary keys, including user prompts and confirmation flows. Fourth, continuity chains: define how an identity can migrate from a compromised key to a new key with verifiable linkage, optionally using guardians or multi-party confirmations. This NIP focuses on interoperability and operational safety rather than ideology.

## What this NIP solves in general

At scale, the network’s health depends on key hygiene. If a non-trivial share of users lose keys or get compromised, the network becomes noisy, spammy, and trust collapses. Today, Nostr’s typical advice is “be careful”. That does not scale. X11 makes safe practices normal: clients can use remote signers, apps can request delegated keys instead of root keys, and users can recover from compromise without losing their social graph. This also reduces spam and abuse indirectly, because compromised accounts are a major vector for “trusted spam”. Continuity chains let clients and relays treat a migrated identity as the same person under clear rules.

## Practical example of problems

A user installs a new mobile client and enters their main key. The client has a bug or is malicious, and the key is exfiltrated. The attacker posts spam, deletes content, changes relay lists, and damages reputation. The user’s only option today is to abandon the pubkey and start over, losing followers and trust. With X11, the mobile client would instead request a delegated session key for posting only, valid for 30 days, with no authority to delete or rotate identity metadata. The main key remains in a remote signer or hardware wallet. If compromise still happens, the user can publish a continuity chain event linking old identity to new identity, and clients can automatically follow the migration and warn about the old key.

## What other NIPs this NIP relies on

* NIP-06 (derivation) for scoped key paths if used.
* NIP-26 (delegation) for delegated signing, plus hardening rules.
* NIP-46 (remote signing) for signer separation.
* NIP-01 (signatures) for continuity chain proofs.

---

# X12. Relay Authentication Profile and Capability Grants

## How it’s related to 2WAY

2WAY treats authorization as explicit state, not a relay operator’s hidden rules. The design includes ACL objects and clear permissions semantics, meaning permission checks are data-driven and verifiable.  Nostr relays increasingly need auth and access control for private communities, paid relays, and abuse prevention, but today it is fragmented. X12 brings the 2WAY idea of explicit authorization into Nostr by standardizing an AUTH profile and signed capability grants. It makes “who can do what” interoperable rather than proprietary.

## The NIP idea

Define two layers. First, a practical AUTH profile: specify the exact client and relay behavior for authentication, including handshake expectations, failure codes, and how auth interacts with subscriptions and writes. Second, capability grants: define a signed object that grants specific permissions, for example read access, write access, moderation rights, posting within a namespace, or access for a limited time. Capabilities must be verifiable offline by clients and relays using signatures, and must carry explicit constraints like target relay or namespace, expiry, and permitted actions. The NIP must define how capabilities are presented to relays, whether as tags or wrapped events, and how relays advertise they support capability-gated operations.

## What this NIP solves in general

Nostr needs private and semi-private spaces to scale socially. Without interoperable auth, every community becomes a custom app or a custom relay, fragmenting the ecosystem. Capability grants allow decentralized access control without central account systems. They also allow relays to price services without breaking clients. Standard auth behavior also reduces confusing UX where clients “sort of work” on some relays but fail silently on others. This is high impact because it supports sustainable relay operations, reduces spam exposure, and enables real communities to exist without reverting to centralized platforms. It also aligns with the network’s ethos: permissions are cryptographic and portable rather than platform-owned.

## Practical example of problems

A paid relay wants to allow posting for subscribers and allow reading for everyone. Today it might implement custom headers, custom tokens, or out-of-band accounts. Most clients do not support it, so users can only participate through a specific client or web app. That fragments the network. With X12, the relay can require AUTH for posting and accept a signed capability token as proof of posting rights. Any client that supports the NIP can use the relay. A private community can issue time-limited moderation capabilities to moderators without sharing root keys. If a moderator is compromised, the capability expires or is revoked, limiting damage.

## What other NIPs this NIP relies on

* NIP-42 for baseline auth concepts if used.
* XX2 for structured auth-related rejections and backpressure.
* X10 if admission control uses auth tiers.
* X14 if sensitive capabilities are wrapped for privacy.

---

# X13. Privacy Baseline: Encryption Profiles per Use Case

## How it’s related to 2WAY

2WAY treats message confidentiality and integrity as default and applies signing and encryption consistently to both user messages and system messages.  The key point is consistency: encryption is not a vague feature, it is a profile with invariants that implementations must share. Nostr’s private messaging ecosystem has suffered from fragmentation and incompatible variants. X13 applies the 2WAY discipline by specifying a small number of encryption profiles, one per use case, so that “encrypted” actually means interoperable and predictable.

## The NIP idea

Mandate that for each private operation class, there is a single standard encryption profile. Examples: direct messages, group messages, capability grants payloads, private moderation commands, and any sensitive state updates. The profile must define the cryptographic primitive version, key agreement method, padding rules if relevant, content encoding, and error handling. It must also define how clients signal support and how they fall back. If multiple versions exist, the NIP must specify negotiation and deprecation rules to avoid long-lived fragmentation. The NIP should also specify rules to minimize accidental metadata leakage inside ciphertext, for example discouraging plaintext tags or unencrypted duplicates of sensitive fields.

## What this NIP solves in general

Encryption that is not interoperable is worse than no encryption because it creates false confidence and fragments the network. When different clients implement different payload rules, users experience “I can decrypt some messages but not others”, and developers keep shipping compatibility hacks. At scale, this becomes a trust and safety issue, not just a feature issue. X13 fixes that by forcing convergence on shared profiles. It also makes auditing easier because there is a known target behavior rather than many ad hoc implementations. This is high impact because private messaging, private community operations, and private credentials are essential for real usage, not niche features.

## Practical example of problems

Two clients both claim to support encrypted DMs. User A sends a message from Client 1, User B opens it in Client 2, and it fails to decrypt because Client 1 used a slightly different encoding, padding scheme, or tag convention inside the ciphertext. Users blame Nostr. Or a capability token is “encrypted” but still includes plaintext tags that reveal the target community, defeating the point. With X13, the payload profile is strict. If a message does not match the profile, it is rejected or flagged consistently. If it matches, it decrypts everywhere. That eliminates a large class of interop complaints and reduces the need for app-specific encryption hacks.

## What other NIPs this NIP relies on

* NIP-44 (or the chosen encryption baseline) if you anchor to it.
* XX1 (strict validation) for profile conformance checks.
* X14 if you require wrapped transport for metadata hiding.

---

# X14. Privacy Baseline: Mandatory Wrapping for Sensitive Operations

## How it’s related to 2WAY

2WAY’s networking model is explicitly designed to reduce metadata leakage. It avoids global broadcast, uses a trust-scoped graph, and supports anonymizing transports like onion routing.  That is a statement that metadata is part of the threat model. Nostr often encrypts payloads while leaving kinds, tags, and addressing metadata exposed. X14 maps the 2WAY mindset to Nostr by making metadata-hiding wrappers a default for specific sensitive operations. Encryption alone is not enough if everyone can still infer who is doing what.

## The NIP idea

Define a set of operations that must be transported inside a metadata-hiding wrapper, for example: capability grants, moderation commands, private replies, group membership operations, and any event that would reveal sensitive relationships through tags or kinds. The wrapper should hide the inner kind, tags, and recipients from passive observers and from relays that do not need to inspect them. The NIP must specify how clients create and unwrap, how relays handle wrapped events, how spam controls apply to wrappers, and how recipients discover and validate inner payloads. It must specify which metadata remains visible, such as outer timestamps, and which must be minimized. It must also define compatibility behavior for clients that cannot unwrap.

## What this NIP solves in general

Metadata leakage becomes a scaling liability once adversaries care. Even if message contents are encrypted, tags often reveal who you are talking about, which community you belong to, or who you are moderating. At small scale, people ignore that. At large scale, it becomes a safety issue. X14 closes the gap by standardizing a transport that hides sensitive routing metadata. It also reduces protocol fragmentation because developers stop inventing custom wrappers. This is high impact because it enables private communities and private governance without turning the network into an open directory of social relationships.

## Practical example of problems

A private community issues moderation actions. The content is encrypted, but the event kind and tags reveal the target pubkey or the community identifier. Observers can map moderation relationships and infer membership. Or a capability grant is encrypted but still includes plaintext tags indicating the relay or namespace, letting relays and crawlers build a directory of private spaces. With X14, the sensitive payload is wrapped. Observers see only a generic outer envelope. Only authorized recipients can unwrap and verify the inner action. Communities can function without broadcasting their membership and governance structure to everyone watching network traffic.

## What other NIPs this NIP relies on

* NIP-59 (or the chosen wrapper mechanism).
* X13 for standardized encrypted payload inside the wrapper.
* X10 because wrappers must not become an abuse vector without admission controls.

---

# X15. Relationship Events as First-Class Graph Edges

## How it’s related to 2WAY

2WAY is explicitly a graph system with core primitives like Parent, Attribute, and Edge. The point is that relationships are objects with clear semantics, not implicit meaning extracted from loosely structured tags.  Nostr has grown many conventions that approximate edges, replies, quotes, references, endorsements, but they often remain tag soup. X15 translates 2WAY’s “edges are first-class state” principle into Nostr by defining relationship events with strict meaning and indexing expectations.

## The NIP idea

Introduce a small set of event kinds representing relationships between two identifiers, where the relationship type is explicit and standardized. Examples: reply-to, quote-of, reference-of, endorse, attach, and remove-relationship. The event must carry clear fields identifying the source and target, optionally with context like a comment or weight. The NIP must define how clients should render each relationship, how relays should index them, and how to avoid ambiguity with existing tag conventions. It must define how to represent relationship removal without relying on deletion of the original relationship event, because relationship lifecycle is distinct from content lifecycle. It must define conflict handling if multiple contradictory edges exist.

## What this NIP solves in general

Tag-based relationship inference does not scale because semantics drift and indexing is hard. When relationships are not explicit, clients implement different threading rules, different quote rules, and different assumptions about what is canonical. That leads to broken threads, inconsistent reply trees, and interoperability failure when apps use the same tags differently. Relationship events create a stable graph substrate that higher-level apps can rely on. This is high impact because it unlocks structured applications beyond a feed, and it reduces the number of heuristics clients must implement. It also enables better moderation and reputation systems because relationships become queryable objects.

## Practical example of problems

A client wants to build a reply tree. Today it parses tags that may be incomplete, inconsistent, or used differently across apps. Some relays strip tags or accept malformed ones. Some clients treat “reply” and “mention” differently. Users see threads that fork or collapse incorrectly across clients. Or a quoting convention differs, so a quote appears as a reply in one client and as a standalone post in another. With X15, a reply relationship is a standardized edge event. Threading is computed from explicit edges rather than guesses. Quote and reference relationships can be displayed consistently. Moderation and spam filtering can treat certain edge types differently without inventing custom parsers per client.

## What other NIPs this NIP relies on

* XX1 for strict validation of relationship event structure.
* XX5 for idempotent handling and dedupe of edges.
* NIP-01 as the base event mechanism.

---

# X16. Scoped Ratings and Reputation Signals with Distance

## How it’s related to 2WAY

2WAY includes Ratings as structured objects with explicit scale and relevance, and it treats reputation as a primitive rather than a side effect of follows.  It also uses trust graphs and degree-of-separation to bound influence.  X16 maps those ideas to Nostr by introducing reputation signals that are explicit, scoped, and filterable by distance. The goal is not “global scores”, it is “local trust that composes”, which is the only version of reputation that scales without centralization.

## The NIP idea

Define standardized rating events that target a pubkey, event id, relay, or namespace, with explicit scale, score, and scope. Scope must include whether the rating is intended as personal, community-local, relay-local, or broadly shareable. The NIP must define anti-abuse constraints, such as whether ratings must be signed by known identities, whether they should be weighted by trust distance, and how clients should handle conflicting ratings. The NIP must define query patterns and recommended default filters, for example “show replies only if rated above threshold by my one-hop or two-hop network”. It must define how ratings relate to relationship edges so that trust distance can be computed.

## What this NIP solves in general

Nostr spam and abuse are not solvable only by relay moderation because users operate across many relays. Also, global moderation is politically impossible. The scalable alternative is local reputation that can be computed deterministically by clients using explicit signals. Today reputation is mostly implicit in follow graphs and heuristics, which is weak and easy to game. X16 creates explicit, interoperable signals. It enables clients to build filters that reduce spam without silencing legitimate content globally. It also enables communities to apply their own rating policies while still using standard formats. This is high impact because it addresses the core quality problem without requiring central authorities.

## Practical example of problems

A popular user gets targeted by spam replies. Some clients show all replies, creating unusable threads. Other clients hide replies using proprietary heuristics, leading to inconsistent user experience and accusations of censorship. With X16, clients can apply a clear rule: only show replies if at least N trusted peers rated the author above a threshold, within a trust distance of two hops. A community relay can publish ratings for known spammers, and clients that trust that community can incorporate them. A user can also maintain private ratings that affect only their own view. The result is scalable filtering that is explainable, portable, and not dependent on one centralized blacklist.

## What other NIPs this NIP relies on

* X15 (relationship edges) to compute trust distance and context.
* X10 (anti-abuse) to reduce rating spam.
* XX1 for strict validation of rating event shape.

---

# X17. App Namespace Tag and Collision-Resistant Schemas

## How it’s related to 2WAY

2WAY explicitly isolates applications and plugins using an `app_id` hierarchy and per-app state separation, so that two apps can coexist without semantic collisions.  Nostr apps frequently reuse kinds and tags in ways that collide, because the base protocol is intentionally minimal. At scale, that becomes chaos. X17 translates 2WAY’s app separation principle into Nostr by requiring a namespace identifier for app-defined semantics. That allows clients to route events to the correct logic and avoid misrendering or misinterpreting data from another app.

## The NIP idea

Define a standard tag that identifies an application namespace for any event that uses app-defined schemas or behavior beyond the base NIP semantics. The namespace identifier should be stable and collision-resistant, such as a reverse domain name or a hash of a canonical app descriptor. The NIP must define when the namespace is required, for example for kinds used by multiple apps or for events that define custom validation profiles. It must also define how clients should behave when they see unknown namespaces: store safely, do not render specialized UI, and do not treat as canonical state unless explicitly supported. Relays can optionally index by namespace for efficient querying. This NIP reduces ambiguity without preventing experimentation.

## What this NIP solves in general

Without namespaces, the same kind number or tag pattern can mean different things to different apps. Clients then either misrender or ignore, and developers add fragile detection heuristics. At scale, this prevents interoperability and creates accidental security issues, where one app’s event is interpreted as another app’s control message. X17 prevents that by making semantics explicit. It also improves indexing and caching because clients can partition app data reliably. This is high impact because Nostr is increasingly used as a substrate for many apps beyond social posting, and without a namespace mechanism, the ecosystem either fragments or becomes unsafe.

## Practical example of problems

Two apps both use a custom event kind for “task objects”. One app treats a tag as “assignee”, another treats the same tag position as “deadline”. A client that supports only one app sees the other app’s events and renders nonsense, or worse, treats the event as an instruction and triggers unintended behavior. Or two wallet-related apps reuse tags for “invoice”, but encode values differently, and users lose funds due to misinterpretation. With X17, both apps include an explicit namespace. Clients that support App A ignore App B’s semantics and vice versa. A relay can support indexing per namespace so the client can query only the namespaces it understands.

## What other NIPs this NIP relies on

* XX1 to validate namespace tags consistently.
* XX7 for scalable retrieval of app-scoped feeds, optional but strongly synergistic.
* NIP-01 as the base event envelope.

---

# X18. Deterministic Client Journal and Rebuild Semantics

## How it’s related to 2WAY

2WAY emphasizes auditability and determinism, including a Log Manager concept and state synchronization framed as replayable operations rather than mutable blobs.  This matters because distributed systems must survive reinstalls, migrations, and partial histories. Nostr clients today often behave like “best effort caches”, which causes drift and weird bugs after upgrades. X18 applies the 2WAY “append-only journal plus deterministic rebuild” concept to Nostr clients, so that a client can reconstruct state predictably from events, and so that behavior is consistent across implementations.

## The NIP idea

Define client-side storage and rebuild rules: how to persist events, dedupe them, apply replaceable resolution, apply deletions and tombstones, and compute derived indexes such as threads, notifications, and app-specific views. The NIP must define what derived state is allowed to be cached, and what must be recomputable from the event journal. It must define checkpointing and migration rules, such as storing a schema version and replaying the journal when the client changes its internal indexes. It must define how to handle missing history, including what to do when tombstones exist without targets or when replaceable winners are missing. This NIP is not about relay behavior, it is about making client behavior reproducible.

## What this NIP solves in general

Many Nostr client bugs are “state drift bugs”. A client works for weeks, then after an update, threads break, counts change, deleted posts reappear, or profiles differ until caches clear. This happens because the client treated intermediate derived state as authoritative and lacked a deterministic rebuild procedure. X18 solves that by making the event journal the source of truth and defining how to rebuild derived state. This is high impact because it reduces user-facing instability and reduces developer debugging time. It also enables cross-device consistency, because a client can sync journals and rebuild the same view deterministically, which improves reliability without requiring centralized servers.

## Practical example of problems

A client changes its threading algorithm in an update to better handle mentions. Users upgrade and suddenly old threads show duplicates or missing replies, because the client’s existing local thread index was built under old rules and is never rebuilt. Another issue: the client stored a “deleted” flag only in memory, not in the journal, so after restart deleted posts reappear until the relay sends the delete again. With X18, the client persists the event journal and persists tombstones and replaceable winners deterministically. After an upgrade, it detects an index version change and replays the journal to rebuild the thread index. Users get consistent behavior across restarts and upgrades, and developers stop shipping “clear cache” as a fix.

## What other NIPs this NIP relies on

* XX4 (deterministic replaceable resolution).
* XX5 (idempotent handling).
* XX6 (tombstone and deletion rules).
* XX1 for consistent validation before journaling.

---

# X19. Relay-to-Relay Peering and Replication

## How it’s related to 2WAY

2WAY’s networking model includes multi-hop relay paths bounded by trust relationships and a Server Graph, and it is explicitly designed for resilience without central hubs.  Relay-to-relay replication is the relay-world analogue: it allows relays to form meshes and share load and durability. At scale, clients should not be forced to do all fanout and all redundancy. X19 applies 2WAY’s principle that replication and multi-hop propagation are part of the substrate, not shoved into every application client.

## The NIP idea

Define a relay-to-relay peering protocol for replicating selected event streams. Relays should be able to advertise peering support and policies, including which namespaces or event types they replicate, how they authenticate peers, and how they handle conflict and duplicates. The protocol must include mechanisms to prevent abuse, such as limiting replication scope, using mutual authentication, and using rate limits. It must define idempotent replication semantics and avoid creating loops. It should also define whether replication is push, pull, or hybrid, and how relays provide proofs or receipts that replication occurred. Clients should be able to discover replication relationships to pick relays that offer durability guarantees without relying on a few mega relays.

## What this NIP solves in general

Without replication, each relay is an island, and clients must connect to many relays to get redundancy, which scales poorly and increases metadata leakage. Replication also enables locality: users can post to a local relay that peers with archival relays, rather than posting to giant public relays. This reduces centralization pressure and reduces client complexity. It also improves availability during relay outages, because data exists on multiple relays by design. This is high impact because it changes the economics of the network: running a relay becomes more viable, and users can have stable experience without converging on a few default relays.

## Practical example of problems

A small community runs its own relay. Users post there. Then the relay goes offline for a day, and the community’s content disappears from most clients. Users respond by posting to big relays instead, centralizing the network. With X19, the community relay peers with one or two archival relays and replicates its event streams. Clients can still read from the archival relays when the community relay is down. Or consider users with mobile constraints: they cannot maintain connections to ten relays. With replication, they can connect to one or two relays that peer broadly, and still get durable content. Replication also helps spam defense by allowing “trusted meshes” to exchange only scoped streams.

## What other NIPs this NIP relies on

* XX5 (idempotent semantics) to prevent duplicate replication storms.
* XX2 and XX3 for declared relay policies and pipeline behavior.
* X10 if peering admission control is needed.
* NIP-01 as base event transport.

---

# X20. Relay Retention Contracts and Storage Roles

## How it’s related to 2WAY

2WAY treats durability and storage responsibilities as explicit parts of the system. It is designed to survive node loss and still reconstruct state because storage and synchronization are engineered as first-class concerns.  Nostr often treats retention as “whatever the relay feels like”. That breaks user expectations and increases load as clients repeatedly refetch. X20 applies the 2WAY discipline by requiring relays to declare retention behavior and by defining storage roles so clients can choose relays intentionally, not blindly.

## The NIP idea

Define a standardized retention contract that relays publish. It must include whether the relay is ephemeral, bounded-retention, long-retention, or archival. It must include constraints such as maximum retention days per event type, whether deletions are honored, and whether historical versions of replaceables are stored. It should include whether the relay participates in replication and whether it offers “discovery-first” support, meaning it tries to keep metadata and relay lists longer even if it prunes other content. The NIP must also define client behavior: clients should select different relays for different needs, for example ephemeral relays for chat-like content and archival relays for identity metadata and important posts. This is mostly metadata and behavioral contracts, not new cryptography.

## What this NIP solves in general

Users lose trust when posts vanish unpredictably. Developers waste time debugging “missing events” that are actually retention differences. Relays become overloaded by repeated queries for old content that no longer exists. X20 reduces that friction. It enables clients to build reliable posting strategies: write to at least one archival relay for durability, and optionally to a local relay for latency. It also improves relay economics, because operators can be honest about what they offer and can specialize. This is high impact because durability is a prerequisite for serious usage. If Nostr cannot provide predictable retention patterns, users fall back to centralized platforms.

## Practical example of problems

A user publishes a long-form post and shares it. A week later, many readers cannot find it because the relay they wrote to had a short retention policy and pruned it. Some clients still show it because they cached it, others do not. The user sees inconsistent reality and blames the protocol. With X20, the relay would have declared “7-day retention”. The client would have warned the user or automatically also posted to an archival relay. For identity metadata, a relay might declare “archival for metadata, ephemeral for feed posts”, so clients can ensure profiles remain available even if older feed items are pruned. This reduces surprises and reduces wasted network load.

## What other NIPs this NIP relies on

* NIP-11 for relay metadata publication.
* XX6 for consistent deletion behavior if relays claim to honor deletes.
* X19 if retention is strengthened by replication.

---

# X21. Mesh Transport Topology Gossip and Route Hints

## How it’s related to 2WAY

2WAY networking explicitly relies on graph-based relationships and scoped routing, rather than global broadcast, and supports multi-hop paths through trusted relationships.  That is directly aligned with mesh transport reality, where naive flooding causes broadcast storms. X21 is the “transport side” NIP that matches those principles. It does not change NIP-01 events. It defines how mesh transports can exchange topology hints and route guidance so that message delivery is efficient, resilient, and bounded, instead of exponential flooding.

## The NIP idea

Define an optional mesh transport layer protocol that can carry Nostr messages over local connectivity, Bluetooth, Wi-Fi Direct, or similar. The protocol includes topology gossip: nodes can announce neighbor relationships, and nodes can build a local graph view. It also includes route hints: when sending to a destination, the sender can include a suggested path or next-hop list. Nodes forward along the path rather than broadcasting to all neighbors. The NIP must define versioning and backward compatibility so older nodes can still do naive broadcast if needed. It must define constraints to prevent abuse, such as limiting topology message frequency and validating route hints. It must define a fallback strategy when routes fail.

## What this NIP solves in general

Offline and local-first use is a major growth path for Nostr, but it breaks down quickly if mesh delivery is flooding-based. Flooding creates congestion, redundancy, and exponential retransmits, which kills battery and throughput. Route hints and topology gossip reduce redundant transmissions and make delivery scalable in dense networks. This is high impact because it enables new operating environments: events can propagate in areas with weak internet, at conferences, or in censorship conditions. It also reduces reliance on centralized infrastructure. Even if most Nostr traffic stays internet-based, having a standardized mesh transport unlocks resilience and reduces the ecosystem’s dependence on a few large relay operators.

## Practical example of problems

At a crowded event, 200 phones run a mesh-based Nostr transport. With naive flooding, a single message is broadcast to every neighbor repeatedly. Devices receive the same packet many times through different paths. Battery drains rapidly and latency spikes. Some devices become overwhelmed and drop packets, causing unreliable delivery. With X21, nodes gossip neighbor lists and build a topology graph. When a phone wants to send to another phone, it computes a route and forwards directly hop by hop. Intermediate nodes relay only to the next hop instead of broadcasting. If a hop fails, nodes can fall back to limited broadcast within a small radius. The network stays usable under density.

## What other NIPs this NIP relies on

* XX5 (idempotent handling) because mesh still produces duplicates.
* XX1 (validation) so malformed transport payloads do not corrupt app logic.
* It does not rely on NIP-01 changes, it transports existing messages.

---

# X22. Content Addressing and Chunked Large Object Transport

## How it’s related to 2WAY

2WAY’s design direction explicitly separates canonical state from bulky payloads and emphasizes hybrid storage models where large objects can live off-path while the graph keeps integrity proofs and references.  Nostr’s biggest scaling cost is media and large documents. Without chunking and content addressing, relays become expensive, clients redownload duplicates, and replication becomes wasteful. X22 is the Nostr equivalent of 2WAY’s “store big things separately, refer by hash, keep integrity cheap” philosophy.

## The NIP idea

Define a standard mechanism for representing large objects as content-addressed blobs, referenced by cryptographic hash, with chunking for transport and resumable download. The NIP must define chunk sizes, hash tree or chunk list format, and how clients request and verify chunks. It must define how to associate metadata, such as mime type, size, and encryption state, and how to reuse existing file metadata NIPs where possible. It must define dedupe semantics: identical content should not be reuploaded, only referenced. It should define relay responsibilities: relays may choose not to store blobs but may store references, and clients can use specialized blob stores while keeping the Nostr event as the canonical pointer.

## What this NIP solves in general

Large objects break Nostr scalability because they consume bandwidth, storage, and CPU, and because they encourage centralization around a few “media relays”. Content addressing and chunking reduce costs. Dedupe means the same file posted multiple times is stored once. Chunking means downloads can resume after interruption. Verification means clients can trust integrity without trusting transport. This is high impact because most user traffic is media and long-form content. If you do not solve large object transport cleanly, you either centralize media or you accept a broken experience. X22 also enables better privacy because encrypted blobs can be stored without relays understanding contents, while still being verifiable by recipients.

## Practical example of problems

A user posts a 50 MB video. Some clients upload it to a random server and include a URL in tags. Links rot, servers disappear, and users cannot verify the file they downloaded matches what the author intended. Other relays refuse the size and the post fails. Or the same meme image is reposted thousands of times and relays store it thousands of times, wasting disk. With X22, the video is chunked and addressed by hash. The event contains the content hash and metadata. Clients fetch chunks from any supporting store, verify each chunk, and reconstruct the file. If the download is interrupted, it resumes. If the same video is posted again, it is the same hash and does not require reupload. That is a direct scalability win.

## What other NIPs this NIP relies on

* NIP-94 (file metadata) if used for describing files.
* XX5 for dedupe semantics at the event layer.
* X13 and X14 if large blobs are encrypted and wrapped for privacy.

---

# X23. Proof-Carrying Attestations Container

## How it’s related to 2WAY

2WAY explicitly anticipates proof-carrying operations, including privacy-preserving verification techniques like ZKPs as optional advanced features, because the system is meant to support trust without central operators rewriting reality.  Nostr needs a generic way to attach verifiable claims without every app inventing its own format. X23 is the Nostr translation: a standard container for attestations, signatures, and later zero-knowledge proofs, so that clients can verify claims consistently and so that “trust” can be grounded in cryptographic evidence rather than ad hoc conventions.

## The NIP idea

Define a generic attestation container event type or payload format. It must support multiple attestation types: simple signed statements, multi-signed statements, credential-like claims, and optional proof objects that can be verified without revealing underlying data. The container must include: what is being claimed, who is asserting it, what is the subject, what is the scope, what is the validity period, and how to verify it. It must support attaching proofs to other events, for example “this event was produced by a verified device” or “this pubkey is eligible for this community”. The NIP must define extensibility so apps can define new claim types without breaking old clients. The NIP must also define how relays should treat these events for indexing and abuse control.

## What this NIP solves in general

As Nostr expands beyond social posting, it needs verifiable claims: membership, eligibility, reputation assertions, device attestations, supply-chain style statements, and more. Without a standard container, every domain invents a bespoke format, which fragments clients and makes verification inconsistent. A standard container makes verification interoperable. It also allows progressive privacy: you can start with simple signatures and later add privacy-preserving proofs without rewriting everything. This is high impact because it enables whole categories of “serious” apps that need verifiable statements, and it allows relays and clients to treat some claims as stronger than others without trusting centralized providers.

## Practical example of problems

A community wants to restrict posting to verified members. Today it might rely on a centralized web login, a proprietary token, or a custom tag convention. Clients cannot verify membership consistently, and users cannot carry membership across clients. Or an app wants to prove that a binary release is signed by the maintainer, but there is no standard way to attach that proof to an event. With X23, the community issues an attestation container that asserts membership, signed by the community authority or multi-sig guardians, optionally wrapped for privacy. Any client can verify it and present UX accordingly. For software integrity, a maintainer posts an attestation that a given hash is the official release, and clients can verify signatures before trusting it.

## What other NIPs this NIP relies on

* NIP-01 signatures for baseline verification.
* X14 if attestations need metadata hiding.
* X10 to prevent attestation spam if relays index these heavily.

---

# X24. Atomic Operation Bundles and Dependency Manifests

## How it's related to 2WAY

2WAY treats state change as a deterministic application of well-formed operations, not as a stream of loosely related messages. In the design, complex actions are expressed as a bundle that is validated as a unit before the State Engine applies it, so partial delivery does not leak into user-visible state. That same principle is missing in Nostr today. X24 brings 2WAY's bundling and unit-of-apply concepts to Nostr so multi-step updates can be atomic and consistent.

## The NIP idea

Define a bundle manifest event that lists a set of child event ids, optional ordering, and a bundle policy. Child events include a tag referencing the bundle id. The manifest includes a hash of the ordered list to prevent tampering, and can declare whether the bundle is strict (all-or-none apply) or soft (partial apply allowed). Clients and relays store child events as usual, but only apply stateful effects that are declared bundle-scoped once the manifest and all required children are present and validated. The NIP defines timeouts, missing-child handling, and how to treat late arrivals. It does not invent new event formats, it adds a standard way to express dependency and atomicity across existing events.

## What this NIP solves in general

Many real actions are multi-event: profile update plus relay list change, community policy update plus moderation list change, or a long-form post plus an attachment pointer plus a caption update. Today those actions can arrive out of order and be applied partially, which creates inconsistent UI, mis-synced state, or security gaps. Bundles make complex actions atomic and deterministic without central coordination. They also improve offline sync because clients can queue a bundle and know that the user-visible state will change only when the set is complete. Relays can index bundles for faster consistency checks, and clients can avoid half-applied updates that lead to confusion and bugs.

## Practical example of problems

A user updates their profile picture and display name, and also updates their relay list to include a new relay that hosts the new image. The client publishes three events. Some relays receive the relay list change first and drop the image fetch because the old profile still points to the previous image. Other relays receive the profile update first and show a broken image because the new relay list has not arrived. Followers see a mix of old and new data depending on which relays respond first. With X24, the client publishes a bundle manifest for the profile change and relay list update. Clients and relays wait to apply the bundle until all required events are present, so users see a coherent update instead of partial state.

## What other NIPs this NIP relies on

* NIP-01 (event model and signatures).
* XX1 (validation framework) so bundle members are well-formed.
* XX5 (idempotent handling) so retries do not reapply bundles.
* XX4 (deterministic replaceable resolution) for bundle member conflicts.

---

# X25. Event Type Profiles for Well-Known Kinds

## How it’s related to 2WAY

2WAY treats data as typed operations, not as loosely interpreted blobs. That comes from explicit schemas and core object types, where meaning is attached to the operation type and validated before it affects state. In practice, 2WAY pushes app developers toward explicit profiles for fields, tags, and constraints, and it enforces those centrally. X25 ports that discipline to Nostr by defining validation and meaning profiles for well-known kinds that already exist, so clients and relays stop improvising.

## The NIP idea

Define “event type profiles” for well-known Nostr kinds, without introducing new fields. A profile is a normative rule set describing required tags, allowed tags, tag shapes, content constraints, and render safety rules for a specific kind. It also defines the order of semantic checks after XX1 structural validation. For example, a profile for metadata events would define exactly which tags are allowed, which values must be strings, and what it means to be valid enough to store and valid enough to render. Profiles are published as part of the NIP and can be updated with versioning and deprecation rules. Clients and relays may still accept unknown kinds, but for known kinds they must follow the profile.

## What this NIP solves in general

At scale, most incompatibilities come from “everyone follows NIP-01” but then interprets specific kinds differently. Some accept extra tags, some reject them. Some treat missing tags as defaults, others as invalid. Some render dangerous content, others sanitize. This NIP reduces accidental fragmentation by making common kinds truly common. It also reduces security issues because render safety rules stop being per-client folklore. Once profiles exist, clients can implement fewer heuristics and relays can reject malformed events early, which reduces storage bloat and reduces downstream crashes. It improves user experience because the same event means the same thing in different clients.

## Practical example of problems

Consider a kind used for relay lists or contact lists. One client writes tags with a slightly different shape, another client accepts it but ignores half the fields, a third client treats it as invalid and drops it. The user then experiences missing follows, broken relay sets, and inconsistent discovery. Or consider long-form notes. Some clients allow a tag that implies a content warning, others treat it as a plain tag and show it unfiltered. Users see different content boundaries and different rendering. With X25, the profile defines the exact tag grammar and the render rules. A malformed event fails consistently everywhere. A well-formed event renders consistently everywhere.

## What other NIPs this NIP relies on

* XX1 (validation framework) for structural correctness baseline.
* XX2 (rejection codes) to report profile failures clearly.
* NIP-01 (event model).

---

# X26. Semantic Failure Taxonomy and Prefix Discipline

## How it’s related to 2WAY

2WAY distinguishes hard invalidity from policy or authorization failures. That separation is foundational because it prevents “bad data” from being confused with “not allowed right now”. In 2WAY terms, cryptographic and structural invalidity is different from ACL denial, rate limiting, or admission control. In Nostr, implementations often mix these and return vague failures that clients mis-handle. X26 brings 2WAY’s failure-class discipline to Nostr so clients can take correct action.

## The NIP idea

Standardize failure categories and the allowed use of rejection prefixes. Define that “invalid” is reserved only for structural, canonical id, or signature violations. Define that “policy” covers size limits, timestamp windows, tag count, and kind restrictions. Define that “auth-required” and “restricted” cover authorization and identity gates. Define that “rate-limited” and “overloaded” cover backpressure. Require relays to use only the correct prefix category, and require clients to interpret them consistently. Also define a stable mapping from semantic failures to user-facing messaging, so clients can avoid misleading UI. This NIP does not invent new message types, it standardizes how existing rejection strings are structured and interpreted.

## What this NIP solves in general

When failures are misclassified, clients behave badly. If an auth failure is labeled invalid, clients might permanently blacklist a relay or drop the event locally. If a policy failure is labeled invalid, users think content is corrupt rather than too large or too fast. If overload is labeled policy, clients may not back off and may keep retrying. At scale, this causes cascading instability and user confusion, plus wasted bandwidth and CPU. X26 creates a consistent ecosystem where clients can do the right thing automatically, like retry later, re-authenticate, warn the user to shorten content, or stop because the event is genuinely invalid.

## Practical example of problems

A relay requires authentication for writes. A client posts and receives a rejection message that says “invalid: auth required” or something similarly misleading. The client then marks the event as permanently failed and does not retry after authentication, or it tells the user their key is broken. Another relay rejects because the event is too large, but it returns “invalid” and the client drops it silently. Users then repost repeatedly, creating more load. With X26, auth failures are always auth-required or restricted, policy failures are always policy, and invalid means truly invalid. Clients can prompt for auth, trim content, or back off under load, instead of misdiagnosing the cause.

## What other NIPs this NIP relies on

* XX2 (rejection codes and backpressure) for structured error surfaces.
* NIP-01 (`OK` semantics) as the transport for failure messages.
* NIP-42 if auth-required semantics are used.

---

# X27. Standard Client Retry, Queue, and Backoff Rules

## How it’s related to 2WAY

2WAY treats outbound behavior as a managed pipeline. Messages can be queued, retried, and replayed safely because operations are idempotent and because failure modes are classified. This prevents clients from acting like uncontrolled network blasters. In Nostr, clients often implement bespoke retry logic that causes unnecessary load and user-visible weirdness. X27 applies 2WAY’s disciplined outbound approach by defining how clients should queue, retry, and back off in response to relay signals.

## The NIP idea

Define normative client behavior for handling publish failures and subscription failures. Clients must implement a local queue for outbound events, mark each event with per-relay delivery attempts, and apply exponential backoff for temporary failures like overload or rate limiting. Define a maximum retry window and when the client should stop and prompt the user. Define how clients should behave when multiple relays are configured: try primary write relays first, then fall back to secondary relays if failures are persistent. Define how clients should handle auth-required responses: initiate auth and retry automatically. Define that “invalid” failures must not be retried. Define that “policy” failures may be retried only if the event can be modified, like truncating content, otherwise it must fail clearly.

## What this NIP solves in general

At scale, uncontrolled retry loops are a major source of self-inflicted DoS. When relays are overloaded, clients that retry instantly create more load, making outages worse. Inconsistent retry behavior also causes user confusion because posts appear in some relays but not others, or appear hours later without explanation. X27 improves network stability and user experience. It reduces redundant traffic, improves battery usage, and makes delivery outcomes more predictable. It also encourages clients to implement queueing as a normal feature, which is necessary for offline-first behavior and for stable posting during intermittent connectivity.

## Practical example of problems

A user posts while commuting with flaky internet. The client sends to three relays, one accepts, two fail due to temporary disconnects. The client, lacking a queue, either drops the event or retries too aggressively. If it retries too aggressively, it burns battery and spams reconnect attempts. If it drops, the user’s post is missing for followers who read from the other relays. With X27, the client queues the outbound event and marks that one relay accepted. It schedules retries for the other relays using backoff and stops after a reasonable window, while telling the user which relays succeeded and which did not. The post eventually propagates without harming network stability.

## What other NIPs this NIP relies on

* XX2 and X26 (structured failure categories and backpressure signals).
* XX5 (idempotent semantics) so retries are safe.
* NIP-01 as baseline event delivery.

---

# X28. Subscription Hygiene and Resource Budgets

## How it’s related to 2WAY

2WAY’s design assumes resource constraints and makes defensive limits a first-class concern, including low-memory devices and hostile peers. In that worldview, query and subscription behavior must be bounded and predictable, or the system collapses under load. Nostr subscriptions can be abused by overly broad filters and high-frequency updates. X28 applies 2WAY’s budget discipline by defining subscription limits, client behavior norms, and relay enforcement expectations.

## The NIP idea

Define a subscription hygiene profile. It sets normative guidance and optional hard limits for subscription breadth, such as maximum number of authors, maximum kinds per subscription, maximum time ranges, and maximum active subscriptions per connection. It also defines relay enforcement: relays may reject or close subscriptions that exceed budgets, but they must report it using XX2 and X26 categories. Clients must prefer narrow subscriptions and must shard large queries into bounded windows using pagination or cursors where available. Define a “subscription keepalive” and “subscription refresh” rule so clients do not constantly tear down and recreate broad subscriptions. Also define how clients should throttle live updates, such as batching UI refreshes.

## What this NIP solves in general

At scale, relay load is dominated by broad subscriptions that effectively request a live firehose. Many clients do this unintentionally, and some attackers do it intentionally. Without a hygiene profile, relays either collapse or implement incompatible ad hoc limits. X28 makes expectations predictable. Clients become better citizens, relays become more stable, and operators can capacity plan. It also improves user experience, because narrow queries reduce duplicates and latency, and because the UI becomes smoother when updates are batched. This NIP is high impact because it reduces baseline relay resource consumption without requiring new cryptography or new event formats.

## Practical example of problems

A client opens a subscription for the home feed by querying many authors plus broad time ranges, and it leaves it open for hours. The relay must keep evaluating filters against every incoming event, and the client receives many irrelevant events due to overly broad criteria. Another client opens ten overlapping subscriptions and duplicates traffic. Under attack, a bot opens many subscriptions with empty filters, effectively requesting everything, and the relay burns CPU. With X28, subscriptions have declared budgets. The relay can reject or downscope with a clear reason. The client is expected to split queries by time windows and author sets, and to use cursors for scrolling rather than broad live subscriptions. Load drops sharply.

## What other NIPs this NIP relies on

* XX2 and X26 (structured rejection and closure reasons).
* XX7 (cursor pagination) strongly helps, but is optional.
* NIP-01 subscription model.

---

# X29. Relay Index Capability Advertisement

## How it’s related to 2WAY

2WAY is explicit about what capabilities exist at each layer and what indexes or managers can answer which queries. That avoids hidden assumptions and allows clients to adapt to different nodes. Nostr relays vary widely in indexing and query performance, and clients often assume features like search or tag queries without reliable discovery. X29 mirrors 2WAY’s explicit capability contract by requiring relays to declare what they index and what query types they support.

## The NIP idea

Extend relay metadata to declare indexing capabilities. Examples: whether the relay indexes by author, kind, tag keys, specific tag types like e and p, namespaces from X17, and whether it supports full text search or only prefix search. Also declare retention and backfill constraints as part of the indexing profile, like how far back queries will return results reliably. Define a standard vocabulary so clients can interpret capabilities consistently. Define recommended client behavior: choose relays for different tasks based on declared indexes, for example using a search relay only when needed, and avoiding expensive queries on relays that do not support them. This NIP does not require relays to implement new features, it makes behavior discoverable and interoperable.

## What this NIP solves in general

Clients today either over-query relays, causing load, or they under-query and miss content because they assume capabilities incorrectly. Operators cannot communicate constraints in a machine-readable way, so client developers hardcode behavior, leading to fragmentation and user frustration. X29 fixes the discoverability layer. It allows clients to route queries intelligently, reducing wasted traffic and improving success rates. It also encourages relay specialization, which improves scalability because not every relay must do everything. This is high impact because query routing and capability discovery are core to making a distributed network feel usable without central indexes.

## Practical example of problems

A client adds a relay and assumes it can answer tag-based queries for mentions. The relay actually indexes only authors and kinds, so the client keeps asking for mentions, receiving incomplete results, and the user misses replies. Another client tries to use a relay for search, but the relay does not support it and closes the subscription, causing the client to retry repeatedly. With X29, the relay declares that it indexes authors and kinds only, and does not support search. The client then uses a different relay for search and uses the first relay for feed retrieval. The user experience improves, and the relay load is reduced because clients stop sending unsupported queries.

## What other NIPs this NIP relies on

* NIP-11 (relay metadata base).
* XX2 (structured rejection) for unsupported queries.
* X28 (subscription hygiene) pairs well but not required.

---

# X30. Standardized Event Receipts and Delivery Proof Hints

## How it’s related to 2WAY

2WAY emphasizes receipts, auditability, and verifiable histories so that systems can prove what was accepted and in what order, even under failures. That mindset reduces ambiguity and makes debugging possible. Nostr today often leaves users guessing whether a relay accepted an event, persisted it, indexed it, or propagated it. X30 introduces a lightweight, interoperable receipt concept that aligns with 2WAY’s emphasis on observable state transitions.

## The NIP idea

Define a relay receipt format that can be returned after successful event acceptance, beyond a generic “OK true”. The receipt can include a relay timestamp, a receipt id, and optional hints like “persisted”, “indexed”, or “queued for replication”, without turning it into a consensus protocol. Receipts should be optionally signed by the relay so clients can log them and later present evidence that a relay accepted an event. Define privacy and abuse constraints, like not leaking subscriber counts. Define client storage rules: clients may keep receipts for troubleshooting, for sync reconciliation, or for durability verification across multiple relays. This does not change NIP-01 events. It standardizes an optional proof-of-acceptance artifact.

## What this NIP solves in general

A major practical problem in Nostr is uncertainty. Users post and do not know which relays have the event. Developers debug missing content and cannot distinguish network failure from relay policy rejection from delayed indexing. Receipts reduce ambiguity. They also enable stronger delivery strategies. For example, a client can consider a post “published” only after receipts from at least two relays that claim archival retention. Receipts help relay operators too, because they can measure ingestion and replication pipeline performance. This is high impact because it improves reliability and user trust without requiring global coordination.

## Practical example of problems

A user posts a note. The client sends it to three write relays. One returns OK, one times out, one closes the connection. The user later complains their post disappeared. The developer cannot tell whether the relay accepted and lost it, rejected it, or never received it. With X30, the first relay returns a signed receipt with a timestamp and a receipt id, and indicates it persisted the event. The client stores this and can show the user that at least one relay accepted. If the relay later denies having it, the user can prove acceptance. The client also uses the receipt count to decide whether to retry the other relays, improving durability.

## What other NIPs this NIP relies on

* XX2 and X26 for consistent success and failure classification.
* X20 and X19 if receipts include retention or replication hints, optional.
* NIP-01 event ids as the anchor for receipts.

---

# X31. Network Partition and Offline Posting Semantics

## How it’s related to 2WAY

2WAY is designed to work offline by default and converge later, with explicit handling of partitions, retries, and replay safety. That is not a feature bolt-on, it is a core architectural principle. In Nostr, offline behavior is common in real life, but not standardized, which causes duplicate storms, timestamp weirdness, and user confusion. X31 adapts 2WAY’s partition-aware thinking into Nostr client and relay expectations around offline creation, delayed publishing, and later reconciliation.

## The NIP idea

Define normative client behavior for offline event creation and later publishing. Specify that clients may create events while offline, queue them, and publish when connectivity returns. Define how clients should choose created_at timestamps in offline mode, including guidance to avoid future-dating and to handle clock skew. Define how clients should display “pending” state and later reconcile it with relay receipts and acceptance outcomes. Define relay expectations for accepting delayed events, including policy windows and whether relays should treat delayed events differently. Define dedupe and replay safety requirements so offline retries do not cause duplicates. This NIP is about predictable offline-first UX and network-friendly reconciliation.

## What this NIP solves in general

Without standards, offline posting yields inconsistent timelines and user trust issues. Some clients future-date posts unintentionally due to clock skew, causing feed pollution. Some clients replay events aggressively and cause duplicates. Some relays reject older timestamps, so offline posts silently fail. X31 makes offline behavior reliable. It also helps scale because offline posting reduces the need for constant network connectivity, but only if the later convergence does not create storms or inconsistencies. This is high impact because mobile devices, spotty networks, and mesh transports are common, and users expect apps to behave sensibly under those conditions.

## Practical example of problems

A user drafts and posts several notes on a train with no signal. The client assigns created_at values based on a device clock that is wrong by two hours. When the user reconnects, the client publishes, and the notes appear in the future on some feeds. One relay rejects them due to time window policy, but the client does not explain. Another relay accepts, but followers reading from other relays miss them. With X31, the client uses a safe timestamp strategy, for example anchoring created_at to last-known-good network time when possible. It keeps posts marked pending until receipts arrive. If a relay rejects due to time window, the client reports it clearly and offers to republish with adjusted timestamp if allowed. The user sees predictable outcomes.

## What other NIPs this NIP relies on

* X27 (retry and queue rules).
* XX2 and X26 (clear failure reasons).
* XX5 (idempotent semantics) for safe replay.

---

# X32. Relay Federation Guardrails for Privacy and Metadata

## How it’s related to 2WAY

2WAY’s trust-scoped propagation and avoidance of global broadcast is partly a privacy design. It limits who learns what and when. When you add replication or peering, privacy risks increase because more parties can correlate activity. X32 brings 2WAY’s privacy posture into Nostr relay federation by defining guardrails: what metadata can be shared during peering, how scopes are enforced, and how clients can opt into or out of federation behaviors.

## The NIP idea

Define privacy guardrails for relay-to-relay peering and discovery assist mechanisms. Specify that peering relationships must be declared, and that relays must not silently broaden dissemination beyond declared scopes. Define what metadata is allowed in federation messages, for example avoiding leaking subscriber identities, avoiding leaking full query logs, and limiting topology data to what is necessary. Define how relays should handle wrapped events from X14 during replication, including whether they can replicate without inspecting inner payloads. Define client controls to select relays based on privacy posture, such as refusing relays that replicate broadly without constraints. This NIP is a policy and behavior contract, not a cryptographic overhaul.

## What this NIP solves in general

As Nostr scales, federation will emerge, either explicitly or implicitly through big relays. Without guardrails, federation can turn the network into a surveillance fabric where activity is correlated across relay meshes. That undermines adoption for users who care about privacy and safety. X32 keeps federation compatible with privacy by default. It also reduces operator confusion by clarifying what should and should not be shared. This is high impact because replication and discovery are necessary for scale, but they must not destroy privacy, otherwise users will centralize into walled gardens or leave.

## Practical example of problems

A relay peers with several other relays and replicates widely. It also logs incoming subscriptions and shares them with peers to improve caching. Now a set of relays can infer a user’s interests and social graph by analyzing query logs, even if content is encrypted. Another issue is wrapped sensitive operations. If a relay refuses to replicate wrappers because it cannot inspect them, private community operations fail to propagate. With X32, peering messages avoid sharing query logs and subscriber identities, and peering scopes are declared and enforced. Wrapped events can be replicated as opaque blobs with integrity preserved. Clients can choose relays that align with their privacy posture.

## What other NIPs this NIP relies on

* X19 (relay peering and replication).
* X14 (wrapping) for sensitive operations.
* X29 (capability advertisement) to declare federation posture and privacy features.

---

# X33. Relay Accountability, Transparency, and Operator Signatures

## How it’s related to 2WAY

2WAY’s philosophy includes provenance and verifiable operations so that no operator can rewrite reality unnoticed. That does not mean full consensus, it means auditability and accountability. Nostr relays today can claim policies but change behavior silently, and clients have limited ways to evaluate relay trustworthiness. X33 applies 2WAY’s provenance mindset by introducing operator-signed metadata, policy change logs, and optional transparency artifacts that help clients make informed relay choices.

## The NIP idea

Require relays to sign their NIP-11 metadata with an operator key and optionally publish a change log of policy and capability updates. Define how clients verify the operator signature and how they cache metadata. Define an optional transparency log mechanism where a relay can publish signed statements about retention policies, replication relationships, and enforcement modes, with timestamps. This does not require relays to prove everything, but it provides a consistent signal that can be tracked over time. Define client behavior: warn users when a relay’s signed policy changes materially, like reducing retention from 30 days to 7 days, or enabling broad replication. This NIP increases predictability and reduces surprise.

## What this NIP solves in general

Relay choice is one of the biggest sources of user experience variance. Users often do not know why content disappears or why behavior changes. Operators can also misrepresent capabilities, intentionally or accidentally. X33 makes relay metadata more trustworthy and trackable. It enables client tooling that detects changes, flags risky relays, and recommends alternatives. At scale, this reduces reliance on a few “known good” relays because smaller operators can build credibility through transparent, signed policies. This is high impact because trust in infrastructure is a social and operational requirement, and transparency reduces ecosystem chaos.

## Practical example of problems

A user relies on a relay for archival posting. The relay silently changes retention to 3 days due to cost. Weeks later, the user’s older posts are gone, and followers cannot find them. The user blames the client or the protocol. With X33, the relay’s retention policy is signed and changes are visible. The client notices the signed metadata changed and warns the user before posting, suggesting adding another archival relay. Another example is replication. A relay begins replicating broadly, increasing privacy risk. The client can detect this policy change and prompt the user to reconsider. Operator signatures make it harder for malicious relays to spoof capabilities without detection.

## What other NIPs this NIP relies on

* NIP-11 (metadata base).
* X20 (retention contracts) and X19 (peering) if you want signed declarations for those features.
* XX2 for consistent interpretation of relay policies.

---

# X34. Moderation Decision Objects and Multi-Signature Governance

## How it’s related to 2WAY

2WAY explicitly talks about governance workflows where no operator can rewrite decisions, and about verifiable policies and attestations that can be audited. That maps cleanly to moderation, which is governance in practice. Nostr moderation is currently fragmented and often centralized in client-side blacklists or relay rules. X34 imports the 2WAY governance mindset by defining explicit moderation decision objects that can be multi-signed, scoped, and audited, without requiring global agreement.

## The NIP idea

Define moderation decision events as first-class objects. A decision can target an event id, a pubkey, a namespace, or a relay scope. The decision includes the action type, like hide, warn, label, throttle, or deny posting, plus scope and duration. It also includes signatures from one or more authorities, such as community moderators, relay operators, or delegated roles. Define how clients apply decisions: decisions are policy inputs, not protocol invalidations. Define dispute and override rules, such as allowing users to choose which authorities they trust. Also define privacy modes, where decisions can be wrapped under X14 to avoid leaking sensitive relationships. This NIP is about interoperable governance artifacts, not forcing uniform moderation.

## What this NIP solves in general

Communities at scale need moderation, but global moderation is not feasible. Without standard moderation objects, each community reinvents tooling and clients cannot interoperate. Users end up locked into specific clients or relay policies. X34 enables moderation that is portable and explainable. It also enables multi-signature governance, which reduces abuse by a single moderator and improves legitimacy. This is high impact because it unlocks sustainable communities and reduces harassment, without centralizing the entire network. It also makes moderation auditable, which reduces drama and confusion.

## Practical example of problems

A community wants to suppress spam accounts. Today they either run a private relay with proprietary rules or they publish a text blacklist that clients interpret inconsistently. Users using different clients see different outcomes and cannot understand why content is hidden. With X34, the community publishes moderation decisions signed by its moderator set. A client that trusts that community can apply them consistently, like hiding content from a spam pubkey for 30 days, with a visible reason code and a link to the decision object. Another community can use different authorities and different thresholds. Users can opt in to trusted moderation sources. Multi-signature rules prevent one compromised moderator from silently banning users.

## What other NIPs this NIP relies on

* X12 (capability grants) if moderation rights are delegated.
* X14 (wrapping) for privacy-sensitive moderation.
* NIP-01 signatures as the base verification mechanism.

---

# X35. Community Membership Objects and Access Policies

## How it’s related to 2WAY

2WAY treats permissions as explicit state via ACL-like objects and expects communities and workflows to be expressed as verifiable graph state rather than hidden server configuration. That makes membership and access portable. Nostr communities often rely on out-of-band membership or proprietary tokens, which fragments clients. X35 maps the 2WAY ACL and governance ideas into Nostr by defining membership objects and access policies that clients and relays can verify consistently.

## The NIP idea

Define community membership events and access policy events. Membership events represent that a subject pubkey is a member of a community, possibly with a role like member, moderator, or admin, and possibly with an expiry. Access policy events define what membership implies, like who can post, who can read, who can moderate, and whether content is public or private. Define how membership is issued, for example signed by community authorities, and how revocation works, for example a signed revoke event or expiry. Define how relays enforce community access, such as requiring proof of membership to accept posts in a namespace. Define privacy options using X14 wrappers to hide member lists. This creates interoperable gated spaces without central accounts.

## What this NIP solves in general

Nostr needs scalable communities that do not collapse into proprietary platforms. Without standard membership objects, communities either remain public and spam-prone or become private and locked to one client. X35 enables communities to be private or semi-private while still interoperable. It also supports role-based governance, which is necessary for moderation and administration. This is high impact because it supports sustained group structures, which are how real networks scale socially. It also reduces abuse because access can be gated by membership and capabilities, rather than relying solely on global spam filters.

## Practical example of problems

A private community runs on a relay that requires a secret token. Some clients support it, others do not. Users cannot join with their preferred client, and the community becomes effectively centralized. Another community wants read access public but posting restricted to verified members. They implement custom auth that breaks many clients. With X35, the community issues membership objects signed by its moderators. Users can present membership proofs to relays and clients can verify them. Posting can be restricted to members while reading remains public. Member lists can remain private by using wrappers so observers cannot enumerate membership. Users gain portability and communities gain control without fragmentation.

## What other NIPs this NIP relies on

* X12 (auth and capability grants) for enforcement and delegation.
* X14 (wrapping) to hide membership metadata when needed.
* X23 (attestation container) may be used as a general representation, optional.

---

# X36. Namespace Governance and Policy Layers

## How it’s related to 2WAY

2WAY uses app_id namespaces and expects policies to apply at multiple layers, like per-tenant policy and per-app domain logic on top of shared substrate rules. That separation lets you apply different constraints without forking the protocol. In Nostr, namespaces from X17 need governance and policy layering to be useful at scale. X36 adds a policy and governance layer that mirrors 2WAY’s ability to apply per-scope rules consistently.

## The NIP idea

Define namespace policy events that describe rules for a given namespace. Policies can include allowed kinds, required validation profiles, membership requirements, moderation authorities, rate limits for posting in the namespace, and retention requirements. Policies are signed by namespace authorities and can be multi-signed. Define how clients and relays interpret policies: policies are not global truth, they are constraints within the namespace. Define how conflicts are handled, such as multiple policy versions with deterministic resolution similar to replaceables. Define how policy updates are announced and how clients handle unknown policies. This NIP enables structured ecosystems of apps and communities within Nostr without relying on hidden relay configuration.

## What this NIP solves in general

At scale, you need predictable environments. A wallet namespace should enforce stricter validation and require wrappers for sensitive operations. A community namespace should enforce membership and moderation policies. Without standardized namespace policies, every relay implements hidden rules and clients break unpredictably. X36 makes policy explicit and portable. It enables interoperability across relays because the rules are part of the namespace definition rather than a relay secret. It is high impact because it allows Nostr to host many different application types safely, without forcing one global policy that fits nobody.

## Practical example of problems

An app defines a namespace for task management. Some relays accept its events, others reject due to unknown kinds, and clients cannot tell users why. A community wants to require that posts are wrapped for privacy, but some relays do not enforce it, leaking metadata. With X36, the namespace publishes a policy stating which kinds are allowed and which validation profile must be applied, plus whether wrapping is required. Relays that support namespace policies can enforce them uniformly. Clients can read the policy and warn the user before posting. If the user tries to post an unwrapped sensitive event, the client can refuse locally or wrap automatically. This reduces fragmentation and prevents policy surprises.

## What other NIPs this NIP relies on

* X17 (namespace tag) as the scope anchor.
* X25 (event type profiles) if policies reference profiles.
* X12 and X14 depending on whether policies require auth or wrapping.

---

# X37. Relay Quality Signals and Client Relay Selection Strategy

## How it’s related to 2WAY

2WAY assumes nodes and peers are not equal, and it plans for trust scoring and influence limits. It also assumes the system should help users choose good peers through structured signals and policies. In Nostr, relay selection is often manual and based on reputation, and clients do not have standardized ways to score relay quality. X37 applies 2WAY-style reputation and policy thinking to relays themselves by defining quality signals and client selection behavior.

## The NIP idea

Define relay quality signal events and selection guidance. Quality signals can include uptime observations, latency measurements, acceptance rate, indexing freshness, retention compliance, and abuse handling posture. Signals are published either by clients as local telemetry shared optionally, or by third parties as attestation containers under X23. Define how clients should aggregate signals, such as weighting by trust distance or known authorities. Define a baseline relay selection strategy: pick a small set of write relays with high reliability and retention, pick read relays aligned with social graph, and pick specialized relays for search or archives based on capabilities from X29. Define privacy constraints so telemetry sharing is opt-in and does not leak user behavior.

## What this NIP solves in general

At scale, users cannot manually manage relay quality. Poor relay choice causes missing content, slow feeds, and unreliable posting. It also causes centralization because everyone gravitates to a few known relays. X37 makes relay quality measurable and portable. It allows clients to recommend relay sets automatically, and it allows smaller relays to earn trust through performance and compliance. This is high impact because relay selection is one of the main user-facing failure points. Improving it reduces support burden, improves network health, and reduces reliance on mega relays.

## Practical example of problems

A new user installs a client and accepts the default relay list. Several relays are unreliable, one prunes aggressively, one is slow, and the user experiences missing posts and failed publishes. They conclude Nostr is broken. With X37, the client can select relays based on quality signals, for example choosing write relays with high acceptance rates and declared retention, and choosing read relays that match followed users. If a relay’s acceptance rate drops, the client can suggest replacement. A community can publish recommended relay sets signed by authorities. Users get a stable experience without deep technical knowledge, and the network becomes healthier because clients stop overloading unreliable relays with retries.

## What other NIPs this NIP relies on

* X29 (relay capability advertisement).
* X20 (retention contracts) for quality criteria.
* XX2 and X27 for measurable acceptance and failure categories.
* X23 if third-party attestations are used.

---

# X38. Deterministic Merge Rules for Multi-Relay Views

## How it’s related to 2WAY

2WAY is designed for convergence under partial views. It expects that different peers have different slices of history, and it defines deterministic reconciliation so that merged state is stable. Nostr clients frequently merge data from multiple relays, but merging is often ad hoc, leading to duplicates, missing items, and inconsistent sorting. X38 imports 2WAY’s deterministic merge mindset into Nostr by defining how clients merge multi-relay streams into one consistent view.

## The NIP idea

Define deterministic merging rules for clients that read from multiple relays. Specify that the primary key is event id, and duplicates are no-ops. Specify stable ordering keys, such as created_at with id tie-break, and define how to handle missing created_at sanity. Define how to reconcile conflicting metadata from relays, like if one relay provides an event and another provides a deletion tombstone for it, or one provides a replaceable winner and another provides older versions. Define how to record per-relay provenance, like which relay supplied the event, without treating it as part of the event. Define how to compute view completeness, like “this thread is partial because only some relays were queried”. This improves consistency across clients and across sessions.

## What this NIP solves in general

Users experience Nostr through multi-relay views. If merging is inconsistent, every client feels like a different network. That reduces trust and makes debugging impossible. X38 makes multi-relay merging predictable and stable. It also reduces load because deterministic merging supports caching and incremental updates. It is high impact because it directly improves the core feed and thread UX without changing the protocol. It also complements scale features like relay replication and scoped discovery, because clients need a correct merge layer to benefit from them.

## Practical example of problems

A client reads the home feed from two relays. It sorts by created_at only. Many events share timestamps. The client displays duplicates or unstable ordering that changes on refresh. Replies appear above parents in one view and below in another. A delete tombstone is fetched from one relay but the target event is fetched from the other, and the client shows the deleted content because it does not reconcile tombstones across sources. With X38, the client uses id as primary key, stable ordering with tie-break, and applies tombstones globally to the merged set. The feed becomes stable and consistent. The client can show provenance to help debugging, like “this came from relay X”, without affecting semantics.

## What other NIPs this NIP relies on

* XX4 and XX5 (replaceable resolution and idempotence).
* XX6 (tombstones) for delete reconciliation.
* XX7 (cursor pagination) benefits merging but not required.

---

# X39. Standard Thread Reconstruction and Reply Semantics

## How it’s related to 2WAY

2WAY’s graph model treats relationships as explicit edges, not inferred from ambiguous tags. That is crucial for stable reconstruction of structures like threads. Nostr threads rely on tag conventions that are interpreted differently by clients, and that causes inconsistent trees, missing replies, and broken context. X39 applies the 2WAY “explicit edges and deterministic reconstruction” principle to Nostr threading and reply semantics so clients build the same thread from the same inputs.

## The NIP idea

Define normative rules for thread reconstruction. Specify how clients identify the root, the direct parent, and mentions, and define how to handle missing parents and partial history. If X15 relationship events exist, define how they take precedence over legacy tag inference, while maintaining compatibility. Define how to sort replies in a thread and how to handle ties and late arrivals. Define how clients should render quotes versus replies, and how to avoid misclassification. Define what “thread completeness” means and how clients can indicate partial threads. This NIP focuses on consistent client behavior and is compatible with current event formats.

## What this NIP solves in general

Threads are a core social structure. When threads are inconsistent, discussions fragment and users feel the network is unreliable. Developers then implement complex heuristics, and heuristics differ between clients. X39 standardizes behavior so a thread looks roughly the same everywhere. It also reduces security and abuse issues because attackers often exploit ambiguous threading to inject content into contexts, or to create confusion. This is high impact because it fixes one of the most visible and persistent user experience problems in Nostr. It also reduces developer time spent on bespoke thread logic.

## Practical example of problems

A user replies to a post. One client sets tags in a certain order, another client expects a different order, and a third client treats a mention as a parent. The reply appears under the wrong root in some clients, or as a standalone note in others. In heated discussions, users accuse others of deleting replies or hiding context when it is actually reconstruction differences. With X39, clients reconstruct based on the same rules. If the parent is missing, clients display a placeholder and mark the thread as incomplete instead of misattaching the reply. If a quote is present, it is displayed consistently as a quote, not as a reply. Conversations become coherent across clients.

## What other NIPs this NIP relies on

* X15 (relationship edges) if adopted, optional but strongly recommended.
* XX1 (validation) to ensure tags or edges are well-formed.
* X38 (multi-relay merge rules) improves completeness handling.

---

# X40. Deterministic Notification Semantics

## How it’s related to 2WAY

2WAY’s model emphasizes deterministic derived state. If you rebuild state from the same operations, you should get the same derived outcomes, like counters, indexes, and notifications. Without that, users see inconsistent behavior after restarts and syncs. Nostr notifications are derived state and are currently inconsistent across clients due to duplicates, partial fetches, and different definitions of what counts as a mention or reply. X40 brings the 2WAY determinism mindset to notifications.

## The NIP idea

Define notification categories and triggering rules, such as mentions, replies, reactions, reposts, moderation actions, and membership changes. Specify that notifications must be idempotent, tied to event ids, and should not repeat across duplicates or replays. Define how clients should handle late arrival, like a reply arrives days later and should still generate a notification depending on user settings. Define how to reconcile notifications across multiple relays and across devices, such as by storing notification state in a local journal with deterministic rebuild or by using a standardized “notification read receipt” event that is privacy-aware. Define how clients should handle ambiguous references, like an event that includes a tag but does not match strict rules.

## What this NIP solves in general

Notifications are where users feel reliability. Duplicate notifications, missing notifications, and inconsistent counts make the network feel broken. At scale, duplicates increase due to multi-relay reads, replication, and retries. Without a standard, every client solves it differently and users cannot trust notification state. X40 makes notifications stable and portable. It also improves performance because notification indexing becomes predictable. This is high impact because it improves day-to-day usability and reduces user churn, and it interacts directly with spam defense because abusive notifications are a common harassment vector.

## Practical example of problems

A user is mentioned in a note. They read from three relays. Each relay delivers the same event. One client generates three notifications. Another client generates one but later generates another after a restart because it did not persist notification dedupe state. Another client misses it because it only checks p tags in a certain position. With X40, notifications are keyed by event id and category, and dedupe is mandatory. The client stores that it has notified once. On restart, it rebuilds from the journal and does not notify again. Mention detection uses standardized rules, so the notification triggers consistently. Users get reliable counts and do not get spammed by duplicates.

## What other NIPs this NIP relies on

* XX5 (idempotent semantics).
* X38 (multi-relay merge) and X18 (client rebuild) for consistent derived state.
* XX1 for consistent parsing and mention rules.

---

# X41. Explicit User Consent and Data Minimization Hints

## How it’s related to 2WAY

2WAY’s design includes regulatory compliance goals like data minimization, consent management, and right-to-erasure behavior, even in a decentralized context. That mindset matters because systems that ignore privacy norms fail at mainstream scale. Nostr is public by default, but clients can still implement meaningful consent and minimization patterns, especially around telemetry, relay selection, and metadata exposure. X41 adapts 2WAY’s consent and minimization thinking into Nostr conventions that improve privacy and reduce accidental data exposure.

## The NIP idea

Define a set of client-side and relay-side consent and minimization guidelines expressed in machine-readable hints and optional events. This includes opt-in telemetry sharing, opt-in relay quality reporting, consent prompts when joining communities that require publishing membership proofs, and minimization of query breadth by default. Define how clients should present consent, such as clear prompts before broadcasting sensitive tags, and clear settings for whether to publish read receipts or membership indicators. Define optional events that encode user preferences, like “do not replicate my content beyond these relays”, as a soft preference signal rather than enforceable law. This NIP does not make Nostr private, it makes privacy hygiene systematic.

## What this NIP solves in general

Mainstream users will not accept systems that leak unnecessary information or that silently share telemetry. Relay operators will not accept uncontrolled scraping that resembles surveillance. X41 improves trust by making consent explicit and by encouraging minimization. It reduces unnecessary network load because minimization means fewer broad queries. It also reduces safety risks for vulnerable users by discouraging accidental broadcasting of sensitive relationships, like community membership or moderation actions. This is high impact because it improves social acceptability and reduces the gap between “tech hobby network” and “real-world usable network”.

## Practical example of problems

A client enables relay quality reporting by default and uploads detailed timing and query behavior to a third party. Users never consented, and their social graph can be inferred from which relays they contact and when. Another client joins a private community and publishes membership proofs in plaintext tags, exposing the user’s affiliation. With X41, telemetry sharing is opt-in, with clear explanation of what data is shared. Membership proofs are wrapped by default when possible, and the client warns before posting anything that reveals affiliations. Clients also minimize subscriptions and query breadth by default. Users who need privacy get a safer baseline without needing expert configuration.

## What other NIPs this NIP relies on

* X37 if relay quality telemetry is used, optional.
* X14 for privacy wrappers where needed.
* XX8 and X28 for minimization through fetch discipline and subscription hygiene.

---

# X42. Standard Cross-Client Settings Synchronization

## How it’s related to 2WAY

2WAY treats user settings and workflows as structured state stored and synced consistently across devices, rather than as per-device hidden configuration. That is part of building a system that works across old phones and desktops while staying predictable. In Nostr, users often switch clients and lose settings, mutes, preferences, and relay selection logic. X42 adapts 2WAY’s “settings as portable state” idea into Nostr so cross-client experience is consistent.

## The NIP idea

Define a standardized set of settings events for client preferences, such as mute lists, content filters, notification preferences, preferred rendering modes, and relay selection preferences. These events are replaceable or parameterized replaceable and are meant to be private or semi-private depending on the setting. Define which settings should be wrapped and encrypted by default. Define conflict resolution rules similar to XX4 so multiple devices converge. Define a compatibility approach where clients can store settings they do not understand without breaking, and only apply what they recognize. This NIP focuses on portability and UX, not on forcing uniform UI.

## What this NIP solves in general

Users churn between clients because settings are not portable. That reduces experimentation and locks users into one app, which undermines the ecosystem. It also creates fragmentation because moderation and filters differ by client, and users cannot reproduce the same experience across devices. X42 makes settings portable. It also reduces support burden because users stop asking how to replicate a configuration. This is high impact because it improves adoption and retention. It also strengthens abuse defenses because mutes, blocks, and filter preferences can follow users across clients automatically, rather than being reset with each new device.

## Practical example of problems

A user sets up extensive mutes and filters in one client and uses a second client on mobile. The second client has none of those settings, so the user sees spam and harassment again. They either abandon the second client or the network. Another user changes notification preferences on one device and is spammed on another. With X42, the client stores settings in standardized events. If the settings are sensitive, they are encrypted and wrapped, so relays cannot learn the user’s moderation preferences. When the user logs into another client, it fetches and applies the same settings automatically. The user experience becomes consistent across devices.

## What other NIPs this NIP relies on

* XX4 (replaceable resolution).
* X13 and X14 for encrypted and wrapped settings where needed.
* XX1 for validation of settings event shapes.

---

# X43. Standardized Mute, Block, and Label Objects

## How it’s related to 2WAY

2WAY’s design expects explicit policy objects and structured state for visibility and access control, similar to ACL and rating primitives. That makes moderation and visibility consistent, auditable, and portable across apps. Nostr already has various mute and block conventions, but they are inconsistent and often tied to a single client. X43 brings the 2WAY approach by making mute, block, and label actions explicit objects with clear semantics.

## The NIP idea

Define standardized events for mute, block, and label actions. Actions can target pubkeys, event ids, namespaces, or tag patterns. Each action includes scope, like personal only, shared with trusted group, or community policy, and includes optional expiry. Labels can include standard label types like spam, harassment, impersonation, or sensitive content, plus custom labels under namespaces. Define how clients apply these actions, including precedence rules when multiple sources exist, like personal overrides community labels. Define privacy options, such as keeping personal mutes private via encryption. Define how relays may optionally enforce block lists for writes in a namespace. This NIP aims for interoperability and portable moderation.

## What this NIP solves in general

Without standard moderation objects, users cannot carry safety preferences across clients and communities cannot share policy in a consistent way. Clients implement different blacklists, causing inconsistent experiences and disputes. X43 standardizes the core moderation primitives so users and communities can interoperate. It is high impact because it directly reduces harassment and spam exposure, improves trust, and reduces fragmentation. It also supports higher-level governance systems like X34 by providing common action types and scopes that can be signed by authorities and applied consistently.

## Practical example of problems

A user blocks an abusive pubkey in one client. In another client, the block does not exist because the format is different, so the abuse continues. A community publishes a spam label list, but some clients interpret it as a mute and others ignore it entirely, so spam remains visible. With X43, the block and mute actions are standardized and portable. The user’s block follows them across clients. Community labels are encoded in a consistent format with clear scope, so clients can choose to apply them. The user can also override community labels personally. This reduces confusion and makes moderation more effective without forcing a single global policy.

## What other NIPs this NIP relies on

* X34 (moderation decisions) if actions are issued by communities, optional.
* X13 and X14 if personal lists are private.
* X17 and X36 if labels are namespaced and governed.

---

# X44. Search and Discovery Protocol Baseline

## How it’s related to 2WAY

2WAY is designed to support discovery through scoped graphs and explicit routing, not by defaulting to global broadcast or centralized indexes. In Nostr, search and discovery are often handled by centralized services because relays do not standardize what search means. X44 adapts 2WAY’s “structured discovery layer” idea by defining a baseline search protocol that is explicit about scope, privacy, and abuse controls.

## The NIP idea

Define a baseline search protocol for relays that choose to offer search. Specify query structure, result ordering, pagination, and scope controls. Scope can include specific namespaces, authors, kinds, time windows, or community scopes. Define that search is optional and must be advertised via X29 capabilities. Define privacy expectations, like relays should not require user identity for basic search unless policy demands it, and relays should avoid logging search queries beyond operational needs. Define abuse controls, like rate limits or capability gating for heavy queries. Define how clients should integrate search results into feeds and threads, including marking results as “search discovered” to avoid confusing them with direct relay delivery.

## What this NIP solves in general

Without standardized search, users rely on a few centralized indexers, which creates centralization pressure and inconsistent results. Clients also implement search inconsistently, and users cannot predict what search covers. X44 makes search interoperable and bounded. It encourages a healthy ecosystem of specialized search relays rather than one dominant index. It is high impact because discovery is essential for growth and for utility beyond existing follows. It also improves safety by making search scope explicit and controllable, reducing the chance that private communities are inadvertently indexed.

## Practical example of problems

A user searches for a topic. One client queries a proprietary API and returns results from a single indexer. Another client queries a relay’s ad hoc search endpoint and returns different results. Users see inconsistent reality and assume manipulation. Another problem is privacy. A private community’s posts get indexed by a relay unintentionally, exposing content that was intended to remain scoped. With X44, search is standardized and advertised. Clients can choose search relays consciously. Relays can enforce scoping rules and require capabilities for indexing private namespaces. Search results include scope indicators and are paginated reliably. Users get consistent behavior and communities avoid accidental exposure.

## What other NIPs this NIP relies on

* X29 (capability advertisement) to declare search support.
* XX7 (cursor pagination) optional but useful.
* X36 if search respects namespace policies, recommended.

---

# X45. Secure Link and Media Integrity Signaling

## How it’s related to 2WAY

2WAY emphasizes provenance-aware media and verifiable attestations, where content can be tied to integrity proofs and where users do not have to trust transport intermediaries. Nostr posts often include URLs, and users trust whatever content appears when they click. This is a vector for phishing, content swapping, and malware distribution. X45 applies the 2WAY provenance mindset to Nostr by providing a standard way to bind links and media references to hashes and optional attestations.

## The NIP idea

Define a standard tag format for linking external resources with integrity information. For example, when a post references a file or URL, the event can include a content hash, expected size, media type, and optional signature or attestation from a trusted authority. Clients can verify that downloaded content matches the hash and warn if it does not. Define how this integrates with X22 content addressing, where the hash can refer to chunked blobs as well. Define an optional attestation mechanism using X23 for “this hash corresponds to the official release” statements. Define client UI guidelines for warning users about unverifiable links and for preferring content-addressed media where possible.

## What this NIP solves in general

At scale, security failures become existential. If users are phished or fed malware through Nostr links, they will not distinguish between client bugs and network design. X45 reduces that risk by making integrity verification normal. It does not prevent all scams, but it makes content swapping harder. It also improves caching and dedupe because hashes enable stable referencing. This is high impact because it improves user safety and supports serious use cases like software distribution announcements, where integrity matters. It also supports better media handling, because clients can decide whether to fetch content based on declared size and type.

## Practical example of problems

A user shares a link to a “wallet update”. The URL later serves a different binary, and followers who click get compromised. Another case is image hosting. A URL can serve different content over time, including inappropriate content, and clients cannot tell. With X45, the post includes a hash for the expected content. Clients download and verify. If the content hash does not match, the client warns and refuses to display by default. For official releases, a maintainer publishes an attestation that a hash is the official build, and clients can show a verified badge. Users gain safer link handling without relying on centralized trust.

## What other NIPs this NIP relies on

* X22 (content addressing) strongly complements it.
* X23 (attestation container) for signed integrity claims, optional.
* NIP-94 metadata if used to describe media.

---

# X46. Device and Client Attestation for Risk Reduction

## How it’s related to 2WAY

2WAY aims to support verifiable supply-chain attestations and provenance so users can trust software and actions without trusting intermediaries. That can extend to device and client attestations, where actions are tagged as originating from a known device class or verified client build. In Nostr, compromised clients and malicious clients are a real threat. X46 adapts 2WAY’s attestation theme into Nostr by defining optional device and client attestations that can be attached to events, enabling clients to apply risk-based UI.

## The NIP idea

Define an optional mechanism for attaching attestations to events that indicate the signing environment, like a remote signer, a hardware device, or a verified client build. Attestations are not required for validity. They are optional signals that clients can use for risk scoring, such as “this key was used through a remote signer with user confirmation” or “this event was posted from an unverified environment”. Use X23 as the general container for attestations, and define specific claim types and verification rules. Define privacy controls so users can disable these signals if they are too identifying. Define that clients must never treat lack of attestation as invalid, only as unknown risk.

## What this NIP solves in general

A large fraction of account compromises come from poor signing hygiene. If the network cannot distinguish between safer and riskier signing contexts, users cannot make informed decisions. X46 allows better defense against account takeover and impersonation. It also improves bot identification because bots often operate from non-interactive signers, and that can be signaled. This is high impact because it improves trust and reduces harm without requiring centralized identity. It also encourages better key practices, because clients can reward safer signing with better UX, like fewer prompts or verified badges, while still allowing anonymous usage.

## Practical example of problems

A popular account is compromised and starts posting scam links. Followers cannot tell whether the posts came from the usual secure signer or from a new risky environment. Some clients might notice behavioral anomalies, but it is inconsistent. With X46, the account’s typical posts include a “remote signer with confirmation” attestation. When the attacker posts from a compromised hot key environment without that attestation, clients can warn, like “this post lacks the usual signer attestation for this account”. Another example is impersonation. A fake account claims to be a maintainer. If the real maintainer uses a verified build attestation, clients can highlight that difference. This reduces harm without making attestations mandatory.

## What other NIPs this NIP relies on

* X23 (attestation container).
* X11 (remote signing and scoped keys) if you want strong signer contexts, optional.
* X45 if attested content integrity is also used.

---

# X47. Standard Abuse Reporting and Evidence Bundles

## How it’s related to 2WAY

2WAY’s governance and provenance approach implies that disputes and moderation should be evidence-based and auditable, not purely discretionary and opaque. In Nostr, abuse reporting is currently ad hoc, and evidence is often screenshots and off-chain. X47 brings a 2WAY-style “verifiable evidence object” approach by defining standardized abuse reports and evidence bundles that can be shared with communities and relay operators without centralizing reporting.

## The NIP idea

Define abuse report events that reference target event ids or pubkeys, include a report category, a free-form description, and optional evidence attachments. Evidence attachments can be references to event ids, signed receipts under X30, or content hashes under X45 or X22, to prove what was seen. Define privacy options, such as wrapping reports so only selected moderators can read them. Define how communities and relays can process reports, such as turning multiple reports into moderation decisions under X34. Define anti-abuse controls to prevent report spam, such as requiring membership or capabilities to file reports in a community scope. This NIP creates interoperable reporting flows.

## What this NIP solves in general

Without standardized reporting, moderation is either centralized or ineffective. Users cannot report abuse in a way that is portable across clients and relays, and moderators cannot receive structured evidence. That makes communities brittle and pushes them to proprietary platforms. X47 improves trust and safety at scale. It enables decentralized reporting flows and reduces reliance on screenshots, which are unverifiable and easy to manipulate. It also improves accountability because reports can be audited, and false reporting can be detected if evidence is required. This is high impact because safety is required for mainstream adoption and for stable communities.

## Practical example of problems

A user is harassed in replies. They want to report it to a community moderation team. Today they either send screenshots in a DM or post publicly, both of which are messy. Moderators cannot verify the context reliably because some relays have pruned the posts or because the content has changed. With X47, the user creates a report that references the event id and includes a receipt showing which relay served it, plus a content hash of the offending media if relevant. The report is wrapped so only moderators can read it. Moderators can verify the references and then issue a moderation decision under X34. The flow becomes structured and interoperable.

## What other NIPs this NIP relies on

* X34 (moderation decision objects) for downstream action, recommended.
* X14 (wrapping) for private reporting, recommended.
* X30 and X45 for evidence receipts and integrity, optional.

---

# X48. Verified Service Announcements and Directory Objects

## How it’s related to 2WAY

2WAY aims to reduce repeated reimplementation of service discovery and trust by making identity, permissions, and provenance part of the substrate. In Nostr, services like bridges, media stores, search relays, and community relays exist, but discovery is ad hoc and often centralized in web directories. X48 applies 2WAY’s “discoverable capabilities with trust signals” approach by defining service announcement objects that can be verified and filtered.

## The NIP idea

Define service announcement events for relays and non-relay services, like search endpoints, blob stores, signers, and community gateways. Each announcement includes service type, endpoint information, supported NIPs and capabilities, and optional operator signatures or attestations. Define how clients discover these announcements, such as through trusted curators, through social graph propagation, or through search. Define how to avoid spam and malicious services, such as requiring announcements to be signed by known identities or requiring attestations. Define how clients should use announcements, for example offering users a list of recommended services with trust scores. This NIP reduces reliance on centralized directories and improves interoperability.

## What this NIP solves in general

Service discovery is essential at scale. If users cannot find reliable relays, search services, or blob stores, they will rely on a few central websites that become choke points. X48 decentralizes service discovery while still allowing trust-based filtering. It is high impact because it enables an ecosystem of specialized infrastructure without centralization. It also supports safety, because users can see verified service announcements rather than random endpoints posted in notes. This helps avoid phishing and malicious relays. It also improves client UX because onboarding can be automated through verified service lists.

## Practical example of problems

A client wants to support chunked media upload. It needs a blob store. Today users paste random URLs or rely on a single popular service. That is brittle and unsafe. With X48, blob stores publish service announcements signed by operators. Communities can endorse specific stores by publishing attestations. The client can show a list of blob stores with verified capability claims, and can choose one automatically based on trust signals and locality. Similarly, a new search relay can publish an announcement describing its indexing scope and privacy posture. Users can discover it through trusted curators rather than through random social posts. This reduces central points of failure.

## What other NIPs this NIP relies on

* X29 (capability advertisement) as a model, but X48 extends beyond relays.
* X23 (attestations) for verification, optional but recommended.
* X33 (operator signatures) if used to sign announcements.

---

# X49. Economic Signaling for Relay Sustainability

## How it’s related to 2WAY

2WAY explicitly considers governance and incentives indirectly through influence limits, admission controls, and policy frameworks that allow sustainable operation without central control. Nostr relays need sustainability, and monetization often pushes operators toward proprietary paywalls that fragment clients. X49 uses the 2WAY mindset of explicit policy and capability signaling to define standard economic signals for relays, like pricing tiers, quotas, and payment proofs, without forcing one payment system.

## The NIP idea

Define a relay economic profile that declares service tiers, quotas, and optional payment requirements. For example, a relay can declare free read access, paid write access, or higher quotas for members. The NIP should define a generic way to present “proof of entitlement” without forcing a specific payment protocol, such as accepting capability grants under X12 or accepting a generic receipt object under X23. It should define how clients present this to users, such as displaying pricing, quota, and the user’s current entitlement status. It should also define how relays communicate quota exhaustion and how clients back off or upgrade tiers. The key is standardizing the interface, not the business model.

## What this NIP solves in general

Relay sustainability is a scaling bottleneck. If relays cannot recover costs, the network centralizes into a few subsidized operators. If relays monetize in incompatible proprietary ways, clients fragment and users suffer. X49 provides a standardized economic signaling layer so relays can be sustainable without breaking interoperability. It also improves transparency. Users can understand which relays are free, which are paid, and what they get. This is high impact because sustainable infrastructure is required for scale, and because the alternative is either centralization or a poor quality network.

## Practical example of problems

A relay starts rate limiting heavily because it is overwhelmed. It quietly offers paid accounts through a website, but clients cannot use it because there is no standard proof mechanism. Users see random failures and migrate to mega relays. With X49, the relay declares its tiers and quotas in metadata. The client can show the user that write access requires a capability token, and it can help the user obtain and present that token using X12 flows. When the user hits quota, the relay responds with a structured “quota exceeded” reason and the client offers options, like using another relay or upgrading. This reduces random failures and makes sustainability interoperable.

## What other NIPs this NIP relies on

* X12 (capability grants) as a portable entitlement mechanism.
* XX2 and X26 for structured quota and payment-related failures.
* X33 if economic policies are signed and tracked.

---

# X50. Interoperable Event Compression and Bandwidth Reduction

## How it’s related to 2WAY

2WAY is designed for low-bandwidth environments, older devices, and efficient resource usage. That implies careful attention to bandwidth and CPU costs, and the ability to operate in constrained networks. Nostr at scale can become bandwidth-heavy due to JSON overhead, repeated tags, and multi-relay duplicates. X50 applies the 2WAY efficiency mindset by standardizing optional compression and compact transport encodings for event delivery, without changing the canonical event format.

## The NIP idea

Define an optional transport-level compression profile for websocket and other transports. The canonical event remains NIP-01 JSON for hashing and signatures, but relays and clients may transmit compressed representations, such as compressed JSON frames or a binary encoding that losslessly round-trips to the canonical JSON before hashing and verification. Define negotiation, so both sides agree on the encoding per connection. Define safeguards, such as maximum decompressed size, to prevent zip-bomb attacks. Define how compression interacts with backpressure and message length limits, clarifying whether limits are applied to compressed or decompressed size. Define compatibility so older clients continue using plain JSON. This NIP aims to reduce bandwidth and improve performance in constrained environments.

## What this NIP solves in general

Bandwidth and battery are scaling bottlenecks, especially on mobile and in mesh scenarios. JSON overhead is real, and multi-relay usage multiplies it. Compression reduces costs, improves latency, and makes offline and mesh transports more practical. It also reduces relay egress costs, which improves sustainability. This is high impact because it provides a mechanical efficiency gain without changing the core protocol semantics. It also helps adoption in constrained environments, which is a growth path and a resilience path. The key is strict safety rules so compression does not create new attack surfaces.

## Practical example of problems

A client subscribes to a busy feed and receives thousands of JSON events. On mobile, this burns battery and data. In a mesh environment, it saturates local radio. Relays pay egress costs and cannot scale cheaply. With X50, the client and relay negotiate compression. The relay sends compressed frames that are decompressed client-side into canonical JSON before validation under XX1. The client enforces a maximum decompressed size, preventing decompression bombs. The same events now use significantly less bandwidth. The user gets faster updates and lower battery drain. The relay reduces bandwidth costs. Multi-relay subscriptions become less punishing.

## What other NIPs this NIP relies on

* XX1 (validation) to ensure round-tripped events are canonical.
* XX2 for clear limits and failure reasons, especially around size constraints.
* Transport specs in NIP-01 context, but no changes to event hashing rules.

---

# X51. Interoperable Payment Intents and Settlement Objects

## How it’s related to 2WAY

2WAY deliberately separates *intent* from *settlement*. It treats economic actions as structured operations with verifiable provenance, rather than opaque side effects of external systems. This allows multiple payment rails, receipts, and attestations to coexist without coupling the core protocol to one financial system. X51 applies this principle to Nostr by defining payment intent and settlement objects that are interoperable, auditable, and decoupled from any single payment network.

## The NIP idea

Define standardized payment intent events and settlement confirmation events. A payment intent expresses that a user or service requests payment for a specific purpose, amount, currency or unit, and scope. It does not specify how payment must be made. A settlement object proves that payment occurred, referencing the intent and including evidence such as a receipt hash, invoice id, or third-party attestation. Define optional encryption and wrapping for privacy-sensitive payments. Define how relays and clients treat these events as data, not as enforcement. Enforcement is handled by policy layers like X49 economic signaling or X12 capability grants. This NIP explicitly avoids embedding a payment protocol. It standardizes how payment-related facts are represented and verified.

## What this NIP solves in general

Payments already exist in the Nostr ecosystem, but they are fragmented, client-specific, and often implicit. Without standardized objects, clients cannot interoperate, users cannot audit what they paid for, and services cannot verify entitlements portably. X51 solves this by making payments explicit, verifiable, and decoupled. It enables multiple payment systems to coexist while allowing clients and relays to reason about entitlements and services consistently. This is high impact because sustainable infrastructure and services require payment, and fragmentation around payments pushes the ecosystem toward centralized silos.

## Practical example of problems

A relay requires payment for write access. One client supports it through a custom Lightning flow. Another client cannot, so users are locked out. Another relay accepts payment but provides no portable proof, so users cannot reuse access on another client. With X51, the relay publishes a payment intent stating the required payment and scope. The user pays using any supported method. A settlement object is generated, signed by the payer or a trusted payment processor, and presented to the relay as proof. The relay then issues a capability under X12. The same settlement object can be reused across clients. The user gains portability, and the relay gains verifiable payment proof without proprietary integrations.

## What other NIPs this NIP relies on

* X23 (attestation container) for settlement evidence.
* X12 (capability grants) for access enforcement.
* X49 (economic signaling) to advertise pricing and payment requirements.

---

# X52. Commerce Objects for Goods, Services, and Subscriptions

## How it’s related to 2WAY

2WAY anticipates marketplaces and service exchanges where claims, receipts, and access rights are represented as structured objects rather than implicit trust in platforms. It treats commerce as stateful interactions that can be audited and verified independently of transport. X52 extends that thinking into Nostr by defining commerce objects that represent offers, purchases, subscriptions, and fulfillment, without central marketplaces.

## The NIP idea

Define standardized commerce objects: offer objects, purchase objects, subscription objects, and fulfillment confirmations. An offer describes a good or service, pricing, terms, and delivery conditions. A purchase references an offer and includes buyer intent. A subscription defines recurring access or service periods. Fulfillment confirmations attest that a service was delivered or access granted. These objects reference payment intents and settlements from X51 where relevant. Define how commerce objects can be public, private, or wrapped. Define that these objects do not enforce behavior, they describe facts that clients and services can verify and act upon. This enables decentralized commerce without requiring trusted intermediaries.

## What this NIP solves in general

Today, commerce on Nostr is informal and fragile. People advertise services in posts, accept payment off-protocol, and deliver manually. There is no portable record of what was agreed, paid for, or delivered. X52 introduces structure. It allows commerce to be interoperable across clients and services. It also reduces disputes because terms and fulfillment are explicit. This is high impact because economic activity drives sustainability and growth, and without standardized commerce objects, serious use cases migrate off-protocol.

## Practical example of problems

A developer offers paid API access via Nostr. They announce it in a post and accept payments manually. Users later dispute what they paid for, and the developer has no standardized way to prove fulfillment. With X52, the developer publishes an offer object describing access terms. A user creates a purchase object and pays via X51. The developer issues a fulfillment confirmation and a capability under X12. The entire transaction is represented as verifiable objects. Another client can later show the user their subscriptions and entitlements automatically. Disputes are easier to resolve because the facts are explicit and signed.

## What other NIPs this NIP relies on

* X51 (payment intents and settlement).
* X12 (capabilities for access).
* X23 (attestation container) for fulfillment proofs.

---

# X53. Standard Receipt Objects for Actions and State Changes

## How it’s related to 2WAY

2WAY treats receipts as first-class artifacts. Whether for storage, replication, or governance, the system benefits from explicit acknowledgment that something happened at a specific time under specific conditions. This reduces ambiguity and improves auditability. X53 generalizes that idea in Nostr by defining standardized receipt objects for actions beyond publishing events, including moderation actions, commerce fulfillment, and relay operations.

## The NIP idea

Define a receipt object format that can be used by relays, services, and communities to acknowledge actions. A receipt references the triggering object, includes a timestamp, scope, and outcome, and is optionally signed by the issuer. Receipts can acknowledge event acceptance, moderation decisions applied, subscription changes, commerce fulfillment, or policy enforcement. Define how receipts are stored and how clients use them, for example to reconcile state or show audit trails. Define privacy options, including wrapping receipts when necessary. This NIP complements X30 but generalizes receipts beyond event publishing.

## What this NIP solves in general

Many disputes and bugs arise because users and developers cannot tell what actually happened. Did a relay accept the event or drop it later? Did a moderator action apply or fail? Did a service deliver what it promised? X53 introduces explicit acknowledgments that reduce ambiguity. This is high impact because it improves trust, debugging, and governance. It also enables better tooling, like dashboards showing which relays acknowledged which actions, or histories of moderation enforcement.

## Practical example of problems

A community moderator issues a moderation decision. Some clients apply it, others do not. The moderator is unsure whether relays enforced it. With X53, relays or clients can issue receipts acknowledging application of the decision. The moderator can see which relays accepted and enforced the policy. Another example is subscription changes. A user cancels a paid subscription, but the service continues charging because there is no portable receipt. With X53, the cancellation is acknowledged with a signed receipt that can be verified across clients and services.

## What other NIPs this NIP relies on

* X23 (attestation container) for signed receipts.
* X30 (event acceptance receipts) as a specialized case.
* X34 (moderation decisions) and X52 (commerce) where receipts apply.

---

# X54. Formal Versioning, Migration, and Deprecation for NIPs

## How it’s related to 2WAY

2WAY explicitly plans for evolution. It treats specifications as living documents with compatibility rules, migration paths, and deprecation strategies. That prevents ecosystems from fracturing when designs improve. Nostr currently relies heavily on social consensus and informal practices around NIPs. X54 introduces formal versioning and deprecation rules so the protocol can evolve without breaking clients and relays unpredictably.

## The NIP idea

Define a formal versioning scheme for NIPs, including minor and major revisions. Define what constitutes a breaking change and what does not. Define deprecation rules, such as minimum support windows and how deprecated behavior should be signaled in metadata. Define migration guidance requirements, including example transitions and compatibility shims. Define how clients and relays advertise supported NIP versions, possibly extending NIP-11. This NIP does not centralize authority, it standardizes expectations around change.

## What this NIP solves in general

Without formal evolution rules, changes cause fragmentation. Some clients move ahead, others lag, and users experience inconsistent behavior. Developers are hesitant to improve designs because they fear breaking compatibility. X54 reduces that fear by making evolution predictable. It is high impact because it enables long-term maintenance and improvement of the ecosystem. It also reduces social friction, because debates can focus on design quality rather than fears of breakage.

## Practical example of problems

A new NIP revises how a certain tag is interpreted. Some clients adopt it immediately. Others do not. Users see inconsistent behavior and blame each other. With X54, the new NIP version is explicitly versioned. Clients advertise which versions they support. Relays can signal deprecation warnings when they see old behavior. Migration guidance is published alongside the NIP. Users and developers have time to adapt, and the network converges gradually instead of fracturing abruptly.

## What other NIPs this NIP relies on

* NIP-11 (capability advertisement).
* X29 (capability and index declaration) as a model.
* Applies to all other NIPs as a meta-layer.

---

# X55. Profile and Schema Migration Objects

## How it’s related to 2WAY

2WAY expects schemas and object definitions to evolve, and it anticipates explicit migration steps to move from one schema to another. It avoids silent reinterpretation of old data. Nostr profiles and structured events evolve informally, leading to clients guessing how to interpret legacy data. X55 introduces explicit migration objects so changes are intentional and verifiable.

## The NIP idea

Define migration objects that explicitly declare how one profile or schema version maps to another. A migration object references the old schema, the new schema, and includes transformation rules or notes. Clients can use this to interpret older events correctly or to generate updated equivalents. Migration objects are signed by schema authors or recognized authorities. Define how migrations are discovered and applied, and how clients handle unknown migrations gracefully.

## What this NIP solves in general

When schemas evolve silently, old data becomes ambiguous. Clients either break or invent heuristics. X55 provides a clean way to evolve structured data without breaking history. This is high impact because it supports long-lived applications and data durability. It also reduces technical debt, because developers no longer need to embed legacy hacks forever.

## Practical example of problems

A profile schema adds a new field and changes the meaning of an existing tag. Old clients misinterpret new profiles, and new clients misinterpret old profiles. With X55, the schema author publishes a migration object explaining how to map old fields to new ones. Clients that support migrations can apply them automatically. Clients that do not can at least warn the user that a profile uses a newer schema. The ecosystem moves forward without breaking older data.

## What other NIPs this NIP relies on

* X25 (event type profiles).
* X54 (versioning and deprecation).
* NIP-01 for baseline event structure.

---

# X56. Formal Test Vectors and Conformance Suites

## How it’s related to 2WAY

2WAY treats correctness as something that must be tested, not assumed. It expects formal test vectors and conformance checks so implementations can be verified against the spec. Nostr lacks standardized test suites, leading to divergent behavior. X56 introduces formal test vectors and conformance suites to ensure that NIPs are implemented correctly.

## The NIP idea

Define a framework for publishing test vectors and conformance suites for NIPs. Each NIP may include or reference a set of canonical examples: valid events, invalid events, edge cases, and expected outcomes. Define how clients and relays can report conformance, optionally publishing signed statements of supported test sets. Define that test suites are normative for behavior, not just illustrative. This NIP does not enforce certification, it enables objective testing.

## What this NIP solves in general

Many interoperability issues stem from subtle differences in interpretation. Without test vectors, developers implement what they think the spec means. X56 provides a shared ground truth. This is high impact because it reduces bugs, improves compatibility, and lowers the barrier for new implementations. It also supports security audits, because edge cases are explicit rather than implicit.

## Practical example of problems

Two relays both claim to support a NIP. One accepts a borderline-valid event, the other rejects it. Clients behave differently depending on which relay they talk to. Developers argue about whose interpretation is correct. With X56, the NIP includes a test vector for that case. Implementations can run the suite and see whether they conform. Disagreements become actionable bugs rather than philosophical debates.

## What other NIPs this NIP relies on

* XX1 (strict validation) strongly benefits from test vectors.
* X54 (versioning) to version test suites alongside NIPs.
* Applies to all NIPs.

---

# X57. Graceful Degradation and Partial Support Signaling

## How it’s related to 2WAY

2WAY is designed to operate across heterogeneous environments, including older hardware and partial implementations. It emphasizes graceful degradation rather than all-or-nothing behavior. Nostr clients and relays vary widely in feature support. X57 introduces a standard way to signal partial support and to degrade gracefully without breaking user experience.

## The NIP idea

Define a partial support signaling mechanism where clients and relays can declare which parts of a NIP they support. For example, a relay may support receipt objects but not signed receipts. A client may support reading commerce objects but not creating them. Define how this is advertised, possibly via extended metadata. Define client behavior when encountering unsupported features, such as rendering read-only views, showing warnings, or offering fallbacks. This avoids binary compatibility assumptions.

## What this NIP solves in general

Without graceful degradation, new features fragment the network. Users on older clients see failures or confusing behavior. Developers hesitate to adopt improvements. X57 lowers that barrier. It allows incremental adoption and mixed environments. This is high impact because it enables evolution without mass breakage, which is essential for a decentralized ecosystem.

## Practical example of problems

A new NIP introduces commerce objects. Some clients support them fully, others do not. Without X57, unsupported clients either ignore them silently or crash. Users are confused. With X57, the unsupported client knows it can display offers read-only but cannot process purchases. It shows a clear message. The user can switch clients if they want full functionality, without the network breaking.

## What other NIPs this NIP relies on

* X29 (capability advertisement).
* X54 (versioning and deprecation).
* Applies broadly to many feature NIPs.

---

# X58. Formal NIP Lifecycle and Governance Process

## How it’s related to 2WAY

2WAY’s design documentation emphasizes explicit governance and change control, even in decentralized systems. It does not assume that good ideas magically converge without structure. Nostr NIPs currently evolve through informal discussion and social consensus, which does not scale well. X58 introduces a formal but lightweight governance process for NIPs themselves.

## The NIP idea

Define the lifecycle of a NIP: draft, review, experimental, stable, deprecated. Define criteria for moving between stages, such as implementation count, test coverage, and security review. Define roles like authors, reviewers, and maintainers, without central authority. Define how objections and alternative proposals are recorded. Define how conflicts between NIPs are resolved or merged. This NIP governs the process, not the protocol semantics.

## What this NIP solves in general

As the ecosystem grows, informal governance becomes a bottleneck. Conflicting NIPs linger unresolved. Developers are unsure which NIPs are safe to implement. X58 provides clarity. It is high impact because it improves coordination, reduces burnout, and increases confidence in the protocol’s direction. It also makes it easier for new contributors to understand how to participate constructively.

## Practical example of problems

Two NIPs propose overlapping features. Both are partially implemented. Clients support different ones. Users experience fragmentation. With X58, both NIPs enter a review phase where conflicts are identified explicitly. One may be merged, or one deprecated. The outcome is recorded and communicated. Implementers know which path is endorsed by process, not by rumor.

## What other NIPs this NIP relies on

* X54 (versioning).
* X56 (test suites) as part of acceptance criteria.
* Applies to the entire NIP ecosystem.

---

# X59. Cross-Protocol Bridging and Import Semantics

## How it’s related to 2WAY

2WAY is designed to interoperate with external systems through verifiable imports, without trusting those systems blindly. It treats imported data as scoped, labeled, and optionally attested. Nostr already has bridges to other networks, but they are ad hoc. X59 brings structure to cross-protocol bridging so imported content does not undermine trust or flood the network.

## The NIP idea

Define standard import objects for content bridged from other protocols. An import object references the external system, the original identifier, and includes evidence such as signatures or hashes. Define labeling rules so imported content is clearly marked. Define rate limits and scope constraints to prevent bridge spam. Define how clients render imported content differently, such as with badges or filters. This NIP does not mandate bridges, it standardizes how they represent imported data.

## What this NIP solves in general

Bridges are inevitable, but unstructured bridges cause spam, impersonation, and confusion. X59 makes bridging safer and more transparent. It is high impact because it allows interoperability without collapsing Nostr’s trust model. It also allows users to filter or prefer native content while still benefiting from bridges.

## Practical example of problems

A bridge imports posts from another network. Some clients treat them as native, others block them. Impersonation occurs because usernames overlap. With X59, imported posts are clearly labeled as such, with verifiable origin references. Clients can filter or style them differently. Communities can decide whether to accept imported content. Trust is preserved.

## What other NIPs this NIP relies on

* X23 (attestations) for origin proofs.
* X25 (event type profiles) to define import object shapes.
* X43 (labels) for marking imported content.

---

# X60. Long-Term Archival and Snapshot Semantics

## How it’s related to 2WAY

2WAY distinguishes between live state, durable state, and archival snapshots. It treats long-term preservation as an explicit concern, not an accident. Nostr content durability is currently inconsistent, and users often do not know what will persist. X60 introduces explicit archival and snapshot semantics.

## The NIP idea

Define snapshot objects that represent a point-in-time capture of a set of events, such as a profile state, a thread, or a community ledger. Define how snapshots are created, referenced, and verified. Define how archival relays advertise support and how clients request snapshots instead of full replay. This reduces load and improves durability.

## What this NIP solves in general

Replaying full history does not scale indefinitely. Snapshots allow efficient synchronization and preservation. This is high impact because it enables long-lived applications and reduces storage and bandwidth costs.

## Practical example of problems

A new client wants to reconstruct a large community history. Fetching everything is slow and expensive. With X60, it fetches a recent snapshot and then replays incremental events. The result is faster and more reliable.

## What other NIPs this NIP relies on

* X20 (retention contracts).
* X22 (content addressing).
* X30 (receipts) for snapshot verification.

---

## X61. Social Recovery and Guardian-Based Identity Restoration

### How it’s related to 2WAY

2WAY treats identity as a durable object that can outlive any single signing key. Keys are credentials attached to an identity, not the identity itself. Because keys can be lost, stolen, or rotated, 2WAY models continuity as an explicit state transition that peers can verify by replaying signed operations and attestations. Guardians fit this model as trusted edges that can authorize a controlled transition when the primary key fails. The important part is that recovery is not “ask people on social media to believe you,” it is a signed, replayable, deterministic chain that clients can validate and render consistently.

### The NIP idea

Introduce a recovery framework made of four event types: (1) guardian designation, (2) recovery proposal, (3) guardian approvals, (4) finalized recovery statement. The guardian designation event allows a user to nominate N guardian pubkeys and define a threshold M. It also defines constraints like cooldown between recoveries, proposal expiry, and whether guardians can be rotated without full recovery. The recovery proposal references the original pubkey and a new pubkey, includes a reason code (lost key, suspected compromise, planned rotation), and includes a timestamp window. Guardians issue approval events that reference the proposal id and are individually signed. Finalization is either automatic once M approvals exist, or a separate finalize event by the new key that embeds the approvals as references. Clients treat a finalized recovery as a continuity link: the new key inherits identity display and trust context, while the old key remains historically valid for old events but is marked as superseded for future identity resolution.

### What this NIP solves in general

Nostr key loss currently destroys identity. That is a structural adoption blocker and it pushes people toward custodians, screenshots of nsec, or unsafe backups. Recovery also matters for compromise, because today the only response is to abandon the account and hope followers notice. A protocol-visible recovery mechanism reduces impersonation windows and removes reliance on informal social coordination. It also enables safe key rotation as a normal hygiene practice instead of a risky identity break. The bigger win is consistency: every client can converge on the same answer to “is this the same person as before,” because the chain is signed, thresholded, and machine-checkable.

### Practical example of problems

A contributor loses their phone and their key with it. They create a new pubkey and post “I am the same person” on relays. Some users believe it, others do not. An impersonator posts the same claim. Confusion persists for months, and the person’s reputation fragments. With X61, the contributor had nominated five guardians. They propose a new key, three guardians approve, and clients automatically show a recovered identity badge. Another case is compromise: an attacker steals the key and starts posting scams. Under X61, guardians can approve a recovery to a safe key quickly, and clients can warn that the old key is compromised and should no longer be used to resolve identity, limiting damage. A third case is planned rotation: a high-risk operator rotates keys annually without losing followers because continuity is explicit.

### What other NIPs this NIP relies on

* X23 Attestation container objects (to carry approvals cleanly).
* X54 NIP versioning and deprecation (to evolve recovery rules).
* X14 Wrapping and encryption (to keep guardian sets private if desired).

---

## X62. Automation Disclosure and Bot Identity Contracts

### How it’s related to 2WAY

2WAY assumes heterogeneous actors and treats influence as something that should be bounded and interpretable. In 2WAY terms, a “node” can represent a person, a service, or an automated agent, but policy and rate limits should be able to distinguish them without guessing. That is the core idea behind explicit classifications and policy-aware handling. Translating that to Nostr means bots should not have to pretend to be humans and humans should not have to infer bot behavior from vibes. The network benefits when automation is declared, because then clients, relays, and communities can apply predictable rules and users can make informed choices.

### The NIP idea

Define a bot disclosure event that an identity can publish declaring one of: human, automated, hybrid, delegated (human identity posting through a service). Add optional “behavior contract” fields: intended posting cadence, content categories, whether replies are automated, whether DMs are supported, and whether the identity participates in economic activity. The event is signed by the identity and can be updated. Relays do not enforce honesty at protocol level, but clients and communities can label content and apply policy. Provide a standard tag that allows third parties to label an identity as “suspected automated” with evidence references, so there is a mechanism for dispute and counter-claims. Define client UI expectations: disclosure must be visible and filterable, and default behaviors for muted automation can be standardized.

### What this NIP solves in general

Bots are inevitable and useful, but unmanaged automation destroys trust and attention. Right now Nostr has both extremes: bot spam and bot bans. This NIP enables a middle path where automation can exist openly and still be regulated. It also helps with safety, because scams often look like “human accounts.” If automation is declared, some forms of deception become harder. It improves network health because relays can apply differentiated rate-limits to automated accounts without harming humans, and communities can define policies like “automated accounts allowed only if they declare behavior contracts.”

### Practical example of problems

A price-alert bot posts 200 times a day. Some relays ban it as spam, other relays accept it, and users experience inconsistent feeds. With X62, the bot declares it is automated and declares a cadence. Relays that accept bots can enforce the declared ceiling, and clients can show a bot label and allow users to filter alerts. Another case: a “reply guy” bot auto-replies to trending posts, creating perceived harassment. If the account is declared automated, clients can downrank or collapse automated replies by default. Another case: a human uses a delegated posting service and later claims they never posted certain content. A delegated disclosure clarifies that a service was in the loop, and audits become possible. This reduces confusion and improves accountability.

### What other NIPs this NIP relies on

* X43 Label objects (standardized classification and warnings).
* X26 Standard rejection and policy feedback (relay responses).
* X49 Economic signaling (for automated commerce accounts).

---

## X63. Legal, Policy, and Compliance Notice Objects

### How it’s related to 2WAY

2WAY’s core stance is that real systems operate under constraints like jurisdictions, retention obligations, and operator policies, but those constraints should be declared, auditable, and separable from protocol semantics. 2WAY also separates “declared policy” from “enforced rules,” allowing different nodes to choose which operators they trust. Applying that to Nostr means operators should not hide behind vague terms or surprise moderation. If a relay or service has constraints, users should see them before relying on it. That mirrors 2WAY’s transparency-first approach: make constraints explicit so trust decisions are informed, not accidental.

### The NIP idea

Define a “notice” event type that relays, communities, and services can publish. The notice includes: issuer identity, scope (relay-wide, namespace, community), jurisdiction claims, retention practices, content restrictions, takedown process, dispute contact method, and versioning. It also includes a “not enforced by protocol” flag as a normative statement to prevent misinterpretation. Notices can be superseded by newer notices with explicit references. Clients should display notices when a user adds a relay, joins a community, or interacts with a paid service for the first time. Relays can include a notice pointer in their metadata. This is declarative, not permissioned, and clients can choose how strictly to treat it.

### What this NIP solves in general

Without explicit notices, users experience arbitrary behavior and call it censorship or incompetence. Operators face risk and respond by centralizing or shutting down. This NIP improves informed consent and reduces surprise. It also helps interoperability: clients can show consistent UX around “what rules apply here.” At scale, legal ambiguity becomes a serious friction that pushes infrastructure toward corporate silos. Transparent notices do not solve law, but they reduce confusion and encourage competitive pressure toward better operator behavior. It also clarifies which relays are suitable for which content categories, reducing conflict.

### Practical example of problems

A user posts content that is legal in their country but illegal in the relay’s jurisdiction. The relay deletes it. The user loses trust and claims a conspiracy. With X63, the relay had a published notice stating jurisdiction and takedown policy, and the client showed it on relay add. The user can choose another relay for that content. Another example: a relay retains IP logs for abuse response. Some users want that, others do not. The notice makes it visible. Another example: a community has stricter rules than the relay and enforces them via moderation events. The community notice clarifies standards, dispute path, and what happens on violation. Users can opt in knowingly.

### What other NIPs this NIP relies on

* NIP-11 relay metadata advertisement (to reference notices).
* X33 Operator signatures (to authenticate issuer role).
* X20 Retention contracts (to align retention claims with behavior).

---

## X64. Deterministic Export and Portability Bundles

### How it’s related to 2WAY

2WAY is built around user control and portability. State is structured, verifiable, and exportable because the system expects nodes and devices to come and go. A user must be able to move clients or rebuild a device and still keep preferences, social graph, and policies without begging a provider. That maps cleanly to Nostr, where “your identity” is not just your pubkey. It is also your follows, mutes, lists, UI settings, relay preferences, moderation preferences, and sometimes paid entitlements. 2WAY would treat those as state objects. This NIP does the same for Nostr clients.

### The NIP idea

Define a signed export bundle format that can carry multiple categories of user state: follows, lists, mute rules, relay choices, topic filters, moderation preferences, and local settings. The bundle is deterministically ordered, includes hashes for integrity, and can be partially exported by category. The format supports encryption for sensitive categories and supports incremental exports, for example “changes since last export.” Import rules are defined: idempotent merge for sets, deterministic last-write-wins or explicit conflict prompts for scalar settings, and strict validation for malformed entries. The export is signed by the identity key or a designated device key. Clients must be able to export and import without relying on any relay.

### What this NIP solves in general

Client lock-in is often invisible. Users leave one client and discover they lost years of tuning and safety settings. That discourages experimentation and concentrates power. A deterministic export format restores user sovereignty and makes the ecosystem more competitive and resilient. It also improves disaster recovery: device loss no longer implies rebuilding everything manually. At scale, portability becomes a security issue too, because users cannot easily rehome from compromised clients. This NIP creates a shared base so any compliant client can import state, reducing fragmentation.

### Practical example of problems

A user switches from Client A to Client B. Their mute list, spam filters, relay ordering, and list subscriptions vanish. They get hit by spam again and blame Nostr. With X64, Client A exports a signed bundle, Client B imports and reconstructs state with predictable merges. Another case: a journalist uses strict filters and safe relay sets. Their laptop dies. With no export, their workflow is destroyed. With X64, they restore from an encrypted export. Another case: a user tries a new client but wants a quick rollback if it is buggy. Exports allow safe trial and rollback without social disruption.

### What other NIPs this NIP relies on

* X38 Deterministic merge rules (shared conflict resolution principles).
* X42 Settings sync objects (optional, for ongoing sync).
* X14 Wrapping and encryption (for private exports).

---

## X65. Accessibility Metadata for Assistive Rendering

### How it’s related to 2WAY

2WAY’s “runs on practically any device” claim implies it must support diverse users and constraints. Accessibility is part of that. When data is structured, accessibility metadata is not a UI hack, it is a first-class attribute that clients can render consistently. In 2WAY terms, this is just well-typed attributes attached to content objects, validated early and made available for downstream rendering. Nostr today often treats accessibility as optional per-client behavior. Standardizing it aligns with 2WAY’s approach: encode important semantics explicitly so all clients can handle them.

### The NIP idea

Define optional, standardized accessibility fields for content events: alt text for images, captions for video or audio, language markers, reading complexity hints, and structured content warnings suitable for screen readers. Include guidance on length limits and normalization rules to avoid abuse, for example very large alt text used as spam. Define strict validation so clients can reject malformed metadata early. Define fallback behaviors: if alt text is missing, clients can indicate “no alt text provided.” If language is missing, clients should not assume English. Allow accessibility metadata to be wrapped when content is private. Provide a minimal conformance target so even lightweight clients can implement the basics.

### What this NIP solves in general

Without standardized accessibility metadata, assistive technologies break and accessibility becomes fragmented. Users who rely on screen readers or captions are effectively excluded. This is high impact for adoption and legitimacy. It also improves content quality for everyone, because captions and language markers enable better search, translation, and summarization. Making metadata explicit avoids per-client reinvention and reduces inconsistent UX. It also reduces legal risk for operators and services that want to be accessible by default.

### Practical example of problems

A visually impaired user scrolls a feed filled with images containing text. Without alt text, the content is meaningless. With X65, authors can attach alt text as a standardized field and clients render it consistently. Another case: a video is posted without captions. Deaf users cannot follow it. With X65, captions can be included or referenced, and clients display them in a predictable way. Another case: a multilingual community shares posts. Without language markers, translation tools misfire and search results are noisy. With X65 language tags, clients can filter or translate properly. These are not edge cases, they are daily usability failures at scale.

### What other NIPs this NIP relies on

* X25 Event type profiles (so accessibility fields are scoped clearly).
* X44 Search and indexing declarations (language-aware indexing).
* XX1 Strict validation pipeline (so metadata is consistently validated).

---

## X66. Locale and Time Context Signaling

### How it’s related to 2WAY

2WAY avoids hidden assumptions in distributed systems. Time, locale, and context are common sources of ambiguity that cause inconsistent derived state. In a 2WAY-style system, events carry enough structured context to avoid interpretation drift across clients. Nostr’s global usage makes this especially important. Locale is not about forcing identity disclosure. It is about optionally attaching context so interpretation is consistent when needed. That matches 2WAY’s approach: make important context explicit and allow privacy-preserving defaults.

### The NIP idea

Define optional locale metadata fields for events: language, region, timezone, and an optional “context hint” category such as “calendar reference,” “local news,” or “local commerce.” Define normalization rules, for example BCP47 for language tags and IANA timezone identifiers. Provide a privacy model: locale fields are optional, can be coarse-grained, and can be wrapped in encrypted events. Define client behaviors: use timezone context for rendering time references, offer translation suggestions based on language, and enable filters like “show me posts in my language” without requiring global inference. Define strict validation so malformed locale fields do not become new attack surface.

### What this NIP solves in general

Global networks suffer from context collapse. Ambiguous time references, language misclassification, and region-specific expectations lead to misunderstandings and poor UX. This NIP improves clarity and improves tooling for translation and search. It is high impact because it reduces friction for non-English users and makes Nostr feel less like an English-default niche. It also improves commerce and community coordination because scheduling and local relevance become machine-handled rather than guessed.

### Practical example of problems

A user posts “tomorrow at 9” about a meetup. Readers in other timezones misinterpret it. With X66, the event can include a timezone, and clients render “tomorrow at 9 local time, Amsterdam,” or convert it. Another case: a post is in Dutch but lacks language metadata. Some clients run translation unnecessarily, others do not. Search results are polluted. With X66 language tags, clients handle it consistently. Another case: a seller posts a local offer that is only meaningful in one country. Locale metadata allows clients to downrank it for distant users or label it clearly, reducing annoyance and spam perception.

### What other NIPs this NIP relies on

* X44 Search and indexing declarations.
* X65 Accessibility metadata (shared language tag usage).
* X14 Wrapping (to keep context private when needed).

---

## X67. Deterministic Rendering Hints and Layout Semantics

### How it’s related to 2WAY

2WAY separates semantics from UI while still enabling consistent derived views. When state is structured, it is possible to standardize some presentation-relevant hints without turning the protocol into a UI spec. The key is safety: hints must not change meaning and must not become a covert channel for abuse. This matches 2WAY’s notion of typed attributes and strict validation. In Nostr, inconsistent rendering leads to miscommunication and fragmentation. A small set of safe hints can improve cross-client consistency while preserving client freedom.

### The NIP idea

Define an optional set of rendering hints that can be attached to content events: suggested grouping of sections, explicit line-break semantics, content block types (paragraph, quote, code, list), and media placement hints. The hints are advisory. Clients may ignore them. However, if a client supports them, it must interpret them deterministically according to the spec. Define strict limits to prevent spam and layout abuse, such as maximum blocks, maximum nesting, and allowed block types. Require that the raw content remains the canonical meaning, and hints only improve formatting. Define validation and downgrade behavior: if hints are invalid, clients should render raw content and optionally show a warning.

### What this NIP solves in general

Today, the same event can look radically different across clients. That causes confusion, especially for long-form content, technical posts, and structured announcements. Without standardization, authors target one client and everyone else gets a degraded experience. This NIP improves readability, reduces misunderstanding, and makes long-form and technical content more viable. It is high impact because better content quality leads to better retention, and consistent rendering reduces support burden for clients and authors.

### Practical example of problems

A developer posts a technical writeup with code blocks. Client A renders code correctly. Client B collapses whitespace, destroying code meaning. With X67, code blocks can be explicitly marked, and clients that implement the hint render it consistently. Another case: an author posts a structured announcement with headings and bullet points. Some clients render it as an unreadable wall. Hints enable consistent block segmentation. Another case: scammers exploit rendering quirks to hide text or create deceptive layouts. Strictly limited hint types and validation reduce those tricks, because clients can fall back to raw content on invalid hints.

### What other NIPs this NIP relies on

* XX1 Strict validation pipeline.
* X25 Event profiles (to scope hint usage).
* X26 Policy feedback (optional, for relays rejecting abusive hints).

---

## X68. Feed Ranking Signal Objects and Explainable Relevance

### How it’s related to 2WAY

2WAY treats ranking and relevance as derived state, and it encourages systems to expose the inputs that lead to ranking decisions so behavior is explainable and auditable. The idea is not one global algorithm, but a shared language for signals. In 2WAY, ratings and reputational edges can be applied as structured inputs while each application chooses how to compute views. Nostr feeds are currently opaque and client-specific, which fuels distrust and manipulation. X68 introduces a standard signal layer that clients can use to build explainable ranking.

### The NIP idea

Define standardized “ranking signal” event types that express inputs like endorsement strength, topical relevance, freshness preference, and relationship-based weighting. Signals can be issued by users, communities, or services, and they reference target events or authors. Signals include scope tags like “for my feed,” “for this list,” or “for this community.” Define anti-abuse constraints: rate limits, optional proof requirements, and clear labeling of who emitted the signal. Define client behavior: clients can choose algorithms, but if they claim to use signals, they must expose which signals affected ranking for a given item. This keeps freedom while making manipulation harder.

### What this NIP solves in general

Opaque ranking creates suspicion and encourages conspiracy thinking. It also makes it hard to debug feed quality, because users cannot tell whether their inputs matter. Standard signals let users and communities shape feeds without relying on centralized recommenders. This is high impact because feed quality is attention, and attention is network survival. It also enables new products: curated feeds as interoperable objects instead of proprietary algorithms. At scale, it reduces spam effectiveness because spam cannot easily fake trusted signals without being visible.

### Practical example of problems

A user complains that their feed is full of low-quality reposts. Client A has a hidden algorithm that downranks them, Client B does not, and users think “Nostr is random.” With X68, users can subscribe to a curated signal set from a community that downranks repost spam. Another case: a political community wants to highlight verified announcements. They publish signals for certain authors and events, and clients can choose to apply them. Another case: a scammer boosts their posts via bot likes. If those likes are expressed as ranking signals, the source identities and patterns become easier to detect and filter, and clients can discount signals from low-trust sources.

### What other NIPs this NIP relies on

* X21 Reputation and trust edges (to weight signals).
* X43 Labels (to mark signal sources or suspicious behavior).
* X38 Deterministic merge (to reconcile competing signal sets).

---

## X69. Ephemeral Content and Expiration Semantics

### How it’s related to 2WAY

2WAY models lifecycle and retention explicitly: data can be durable, revocable, expiring, or policy-bound. It does not rely on “best effort deletion” that different nodes interpret differently. In Nostr, “ephemeral” behavior is currently inconsistent and often illusory, because once something is relayed it can persist indefinitely. X69 borrows the 2WAY idea that expiration must be declared as part of the object’s semantics, and that clients and relays need consistent rules for how to treat expiring objects and their caches.

### The NIP idea

Define standardized expiration metadata for events: an explicit expiry timestamp, optional expiry conditions, and an intent field describing whether the author expects deletion or only reduced visibility. Define relay guidance: relays may drop expired events from active indexes and may refuse serving them after expiry, but they are not forced to erase all traces. Define client guidance: clients should not render expired events by default, should not forward them after expiry, and should clearly mark them if shown in history. Define consistency rules for quotes, reposts, and references to expired events, including how clients should handle dangling references. Require strict validation of expiry fields and forbid absurd expiry far in the future for “ephemeral” types to prevent abuse.

### What this NIP solves in general

Users need content modes like “story” posts, temporary alerts, and time-limited announcements. Without standard semantics, ephemeral content either persists unexpectedly or disappears unpredictably depending on relay behavior. This damages trust. X69 provides consistent expectations and improves UX for time-bound content, while staying honest about decentralization limitations. It is high impact because it unlocks new use cases like live event coordination, emergency notices, and privacy-respecting temporary communication, while reducing accidental permanence.

### Practical example of problems

A user posts a temporary location during a meetup and expects it to disappear. Months later it is still searchable on a relay archive and someone doxxes them. X69 cannot force deletion everywhere, but it can ensure compliant relays stop serving it after expiry and compliant clients stop rendering and forwarding it. Another case: an alert bot posts frequent “status” messages that remain forever, cluttering profiles. With expiry semantics, clients can treat them as temporary and keep profile history clean. Another case: a community uses ephemeral polls. Without standard rules, poll results and votes linger and get replayed, confusing later viewers. Expiration semantics enable consistent cutoff and UI behavior.

### What other NIPs this NIP relies on

* X20 Retention contracts (relay behavior declarations).
* XX6 Tombstones and revocation semantics (for explicit deletion intents).
* X26 Policy feedback (relays rejecting invalid expiry).

---

## X70. Content Licensing and Usage Rights Objects

### How it’s related to 2WAY

2WAY’s provenance model assumes that objects can carry explicit claims about origin and permitted usage, and that those claims should be verifiable and portable. It avoids relying on platform-specific terms that disappear when a service changes. Nostr content is often reused across contexts, sometimes commercially, and licensing ambiguity causes conflict. 2WAY would treat licensing as a structured attribute attached to content and to derived works, making it discoverable and enforceable by social and legal layers. X70 implements that same approach: explicit rights metadata that travels with the event.

### The NIP idea

Define a license declaration field or companion event that can attach a license statement to a piece of content. The license statement can reference a well-known SPDX identifier, Creative Commons variant, public domain dedication, or a custom terms hash that points to a human-readable document. Define how derived works must reference the license of the source, and how an author can update licensing for future derived works without rewriting history. Define client behaviors: show license badges, warn on reuse, and include license references when reposting or embedding. Define strict validation: license identifiers must be normalized, custom terms must be content-addressed, and conflicting multiple licenses must be handled deterministically.

### What this NIP solves in general

Licensing ambiguity discourages creators from posting high-value work and discourages legitimate reuse. Without explicit terms, people either assume everything is free or assume nothing is reusable. Both outcomes are bad. X70 makes rights clear without central platforms, enabling a healthier creator economy and reducing disputes. It is high impact because it makes Nostr viable for professional publishing, open collaboration, and commercial media where licensing clarity matters. It also reduces risk for apps that want to aggregate or republish content legally.

### Practical example of problems

A photographer posts images. A third party scrapes and sells them as prints. The photographer claims infringement, the scraper claims “no terms were stated.” With X70, the content includes a CC BY-NC license badge, and clients and aggregators can see and respect it. Another case: an open-source educator posts tutorials and wants broad reuse with attribution. The license field supports that, and repost clients automatically carry attribution and license. Another case: a community wants to share public domain historical photos but avoid confusion. Explicit PD dedications prevent later disputes and simplify archiving and republishing workflows.

### What other NIPs this NIP relies on

* X22 Content addressing (hash references to custom terms).
* X25 Event profiles (to standardize license field usage).
* X23 Attestation objects (optional, for third-party rights attestations).

---

## X71. Anonymous Credential Presentation and Selective Disclosure

### How it’s related to 2WAY

2WAY’s privacy model includes the idea that you can prove properties without revealing identity or unrelated data. It anticipates ZK proofs or selective disclosure credentials as first-class mechanisms to satisfy access control, reputation gating, or compliance checks while preserving user privacy. In 2WAY terms, you present a verifiable claim bound to an identity context, but not necessarily revealing the primary identity key. Nostr has growing needs for gated spaces, age checks, membership proofs, and anti-sybil measures that do not require doxxing. X71 implements that privacy-first proof layer.

### The NIP idea

Define a standardized event type for presenting anonymous credentials. The event includes: the proof payload, the claim type (membership, age range, human verification, payment status), the verifier context (who the proof is intended for), and expiry. The proof can be one of several schemes, and the NIP specifies a registry mechanism for proof formats rather than hardcoding one. The event can be wrapped to prevent replay by unauthorized parties. Verification rules are deterministic: clients and services that understand a proof format can validate it locally, and those that do not must treat it as opaque. The NIP also defines anti-replay measures, such as nonce binding or context-binding, so proofs cannot be stolen and reused.

### What this NIP solves in general

Many access control needs push systems toward identity disclosure. That destroys privacy and discourages participation. Anonymous credentials enable a middle path where users can prove they meet criteria without revealing who they are. This is high impact because it unlocks privacy-preserving communities, regulated services, and anti-spam gating while keeping Nostr’s decentralized ethos. It also makes it possible to build safer moderation and safety tools without building centralized identity registries.

### Practical example of problems

A community wants to allow only verified adults to access explicit content, but does not want to collect identities. Today the options are weak: self-assertion, centralized login, or nothing. With X71, a user presents a proof of “age over 18” issued by some credential provider, without revealing name or date of birth. Another case: a paid service wants to grant access only to paid subscribers. Today it might require linking a pubkey and payment account permanently. With X71, the user presents a time-limited proof of payment status that cannot be replayed elsewhere. Another case: anti-spam gating: users present a proof of uniqueness without revealing identity, reducing bot floods while preserving anonymity.

### What other NIPs this NIP relies on

* X14 Wrapping and encryption (privacy and anti-replay).
* X23 Attestation containers (packaging proofs and metadata).
* X12 Capability grants (to turn proofs into permissions).

---

## X72. Proof-of-Personhood and Sybil-Resistance Hooks

### How it’s related to 2WAY

2WAY treats sybil resistance as a layered concern. It does not assume one universal scheme, but it provides places to attach proofs and to apply influence limits based on them. This avoids hardcoding politics into the protocol while still enabling networks and communities to resist cheap fake identities. Nostr at scale faces the same problem: bots and sybil swarms can dominate attention and harassment. X72 aligns with 2WAY by defining standard hooks for personhood proofs that are optional, pluralistic, and visible, enabling policy without forcing a single identity system.

### The NIP idea

Define a standard event type for publishing and presenting “personhood proofs” that bind to a pubkey or to an anonymous credential context. The NIP does not choose a single PoP provider. Instead it defines how proofs are referenced, verified, expired, and rotated. Proofs can be direct attestations, cryptographic tokens, or ZK statements. The NIP defines safety constraints: proofs must be time-bound, revocable, and optionally privacy-preserving. It also defines a standard way for relays and clients to express preferences like “require PoP for posting in this space” or “weight actions higher if PoP exists,” without requiring universal adoption. This is a hook, not a mandate.

### What this NIP solves in general

Sybil attacks are cheap and devastating in open networks. Without any hook, the only defense is heavy moderation, centralized allowlists, or economic barriers that exclude legitimate users. X72 enables flexible, community-driven defenses. It is high impact because it lets different environments choose different tradeoffs: some spaces remain fully anonymous, others require personhood to participate, and still others simply use proofs as ranking inputs. Standard hooks reduce fragmentation and make implementations interoperable rather than bespoke.

### Practical example of problems

A harassment campaign creates 10,000 pubkeys and floods replies. Relays and clients can rate-limit but cannot distinguish genuine users from a swarm. With X72, a community can require a personhood proof for posting, dramatically raising attack costs. Another case: a marketplace wants to reduce fraud. It can require PoP for sellers or weight PoP in reputation scoring. Another case: a political discussion group wants anonymity but not sybils. They can accept privacy-preserving PoP proofs that do not reveal identity but still enforce uniqueness. Without standard hooks, each solution becomes a silo and users must re-verify repeatedly.

### What other NIPs this NIP relies on

* X71 Anonymous credential presentation (for privacy-preserving PoP).
* X21 Reputation and trust edges (to weight proofs).
* X49 Economic signaling (optional, for cost-based sybil resistance).

---

## X73. Cross-Device State Sync and Conflict Resolution

### How it’s related to 2WAY

2WAY is explicitly local-first and multi-device. That implies deterministic convergence when the same logical state is edited in different places, offline, then merged later. 2WAY accomplishes this by strict operation typing, ordering rules, and merge semantics that are consistent across devices. Nostr clients increasingly behave like stateful apps, not just event viewers. They have drafts, settings, lists, filters, and moderation preferences that need to sync across phone and desktop. X73 applies the 2WAY idea that client state must be represented as typed operations with deterministic merge rules, not as “whatever the last device happened to upload.”

### The NIP idea

Define a set of event types for client state updates such as: setting updates, list edits, draft saves, and device presence. Each state update is an operation with a stable target key, a monotonic logical clock or comparable ordering input, and explicit merge policy. Define merge rules by state category: sets are merged by union minus tombstones, scalars use last-write-wins with deterministic tie-breakers, and structured objects use field-level merge with conflict markers. Define a conflict event type that can be emitted when automatic merge is unsafe, allowing user intervention. Define privacy: state events can be wrapped so only the user’s devices can read them. Relays are transport, not authoritative.

### What this NIP solves in general

Multi-device inconsistency is one of the fastest ways to make users lose trust. If your mutes differ per device, you will get spam on one and not the other. If drafts diverge, you lose work. If list edits conflict, you get duplicated or missing entries. Today every client solves this differently, or does not solve it at all. X73 standardizes the state model and merge logic so users can switch devices and clients without chaos. It is high impact because it makes Nostr clients feel like real products rather than fragile viewers.

### Practical example of problems

A user edits a mute list on desktop while offline, then edits the same list on mobile. Later both connect and sync through relays. Without a standard merge, one edit overwrites the other and the user does not notice until spam returns. Under X73, list operations are merged deterministically, and both edits survive. Another case: the user writes a long draft on laptop and short edits on phone. Without conflict handling, the wrong draft version wins and they lose work. Under X73, draft operations can either merge text changes with deterministic rules or emit a conflict object prompting the user. Another case: a user changes relay preferences on one device and expects it everywhere. With standardized state updates, that becomes reliable.

### What other NIPs this NIP relies on

* X38 Deterministic merge rules (shared primitives).
* X14 Wrapping and encryption (private device sync).
* X42 Settings objects (if separated as a dedicated NIP).

---

## X74. Client Plugin Sandboxing and Permission Scopes

### How it’s related to 2WAY

2WAY is built around least privilege and explicit permissions. Access control is not a UI promise, it is enforced by system rules, and components receive only the authority they need. Nostr clients increasingly support plugins, scripts, extensions, and embedded apps. That is a direct path to key theft and silent exfiltration if permissions are not explicit and enforceable. X74 applies the 2WAY philosophy to the client side: plugins are actors, they need scopes, and the user must be able to grant, inspect, and revoke capabilities cleanly.

### The NIP idea

Define a plugin manifest format and a permission model for Nostr client plugins. Permissions are scoped, for example: read public events, read private wrapped events, request signing, access contact lists, access relay configuration, send DMs, perform payments, access local storage. Define runtime requirements: plugins run in a sandboxed environment with clear APIs, no raw key access, and explicit signing requests that show the content being signed. Define consent UX expectations: users must approve scopes at install and on escalation, and can revoke at any time. Define audit logging events or local logs that record plugin actions like signing requests, so users can detect abuse. The NIP does not mandate a single sandbox technology, but it standardizes permissions and expected behavior.

### What this NIP solves in general

Without a permission model, plugins turn clients into malware platforms. The biggest risk in Nostr is key theft, because keys are power. If plugins can request signing silently or access secrets, users will get drained, impersonated, or extorted. This NIP creates an interoperable security baseline so plugin ecosystems can exist without destroying trust. It is high impact because plugin extensibility is attractive, and a single high-profile plugin exploit would harm the entire ecosystem’s credibility.

### Practical example of problems

A plugin claims to provide “better search.” It actually reads the user’s contact list and sends it to a server, then asks for a signing request that the user does not understand, and posts spam as them. With X74, the plugin must declare scopes, and the client can show “this plugin requests contact list access and signing ability.” Users can reject it. Signing requests must be explicit and show what will be signed, preventing blind signatures. Another example: a wallet plugin requests payment access. The permission model can require stronger confirmations and rate limits. Another example: a community plugin wants to auto-moderate. It can be granted only “publish moderation events” scope, not full signing or DM access, limiting blast radius.

### What other NIPs this NIP relies on

* X12 Capability grants (for client-side capability semantics).
* X46 Secure local storage and key handling guidance.
* X26 Policy feedback (optional, for relays rejecting plugin-produced malformed events).

---

## X75. Emergency Network Mode and Graceful Degradation Signaling

### How it’s related to 2WAY

2WAY assumes adversarial conditions and partial failure: DoS, partitions, overloaded nodes, and hostile actors. It includes explicit mechanisms to rate-limit, prioritize, and degrade gracefully instead of failing unpredictably. Nostr at scale faces similar conditions, especially spam waves and relay overload. Without coordinated signaling, clients keep retrying, relays keep dropping, and the system thrashes. X75 mirrors 2WAY’s “operational state is part of the protocol surface” approach by making emergency mode and degradation policies visible and machine-actionable.

### The NIP idea

Define an emergency status event or metadata extension that relays and optionally clients can publish indicating operational mode: normal, constrained, emergency. Include machine-readable hints such as: accepted event kinds reduced, write limits tightened, proof requirements enabled, subscription limits reduced, and recommended backoff intervals. Define a standard “degradation policy” for clients: reduce parallel subscriptions, increase backoff, prefer cached content, and avoid expensive queries. Define transparency requirements: the signal must include a reason code like spam attack, maintenance, or resource exhaustion. The signal does not force clients, but compliant clients should adapt to prevent cascading failure. Signals are time-bound and must be cleared explicitly or expire.

### What this NIP solves in general

When networks are under attack or load, coordination failures create self-inflicted outages. Users see timeouts and assume the protocol is broken. Operators cannot communicate effective mitigations to clients, and clients cannot distinguish “relay is dead” from “relay is intentionally limiting.” This NIP reduces thrashing and makes failure modes predictable. It is high impact because spam waves and overload events will happen repeatedly, and graceful degradation is the difference between a bad hour and a network-wide reputation collapse.

### Practical example of problems

A spam wave hits. Relays start rejecting writes and dropping subscriptions. Clients keep retrying aggressively, amplifying load. Users see endless spinners. With X75, relays publish emergency mode with recommended backoff and reduced subscription guidance. Clients reduce retries, reduce subscription fan-out, and prefer cached feeds. The relay stays partially functional instead of collapsing. Another case: a relay is doing maintenance and temporarily restricts writes. Users interpret it as censorship. With emergency signals including maintenance reason, clients can show “relay in maintenance, retry later,” reducing conflict. Another case: a relay enables stricter anti-spam proofs temporarily. With emergency signaling, clients that support the proofs can switch modes automatically, while others can route around rather than failing unpredictably.

### What other NIPs this NIP relies on

* XX2 Network hygiene and backoff rules (client behavior baselines).
* X26 Policy feedback (structured rejection reasons).
* X49 Economic signaling or proof hooks (optional, for emergency anti-spam measures).








