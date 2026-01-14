



# NIPs by Tim

This repo contains a set of draft NIPs, all work in progress. Together they explore how Nostr could gain stronger and more predictable guarantees around identity, permissions, ordering, privacy, and durable state across peers, without changing Nostr’s core model or culture. The work is grounded in ideas I previously developed for 2WAY, which is built around strict boundaries, ordered pipelines, explicit invariants, and deterministic outcomes so that different implementations converge on the same result.

Rather than importing 2WAY as a system, I am treating it as a source of constraints. The work starts from concrete 2WAY concepts, such as a defined ingress pipeline, deterministic resolution of replaceable events, explicit deletion and visibility rules, or structured policy feedback, and then translates those ideas into Nostr terms. That means asking what they should look like as events, tags, relay behavior, client guarantees, and failure modes inside the existing Nostr event and relay model.

Across the full set of ideas outlined here, the goal is to make implicit assumptions explicit. Many behaviors that exist today only as conventions, client heuristics, or relay-specific rules are candidates to be turned into documented, testable expectations. Examples include how events are validated and rejected, how relays signal overload or policy limits, how replaceable state converges across relays, how deletes and tombstones affect visibility, how pagination and replay behave, and how clients should react to partial failure instead of guessing.

Several of the proposed areas focus on convergence and correctness. These cover strict validation boundaries, ordered relay ingress and egress stages, idempotent replay, deterministic rebuild of client state, and stable merge rules when data arrives from multiple relays. The intent is that two compliant clients, connected to different but overlapping relay sets, still reconstruct the same logical state from the same events.

Other areas focus on safety, privacy, and abuse resistance. These ideas include clearer authorization and capability patterns, safer key usage and delegation models, explicit privacy profiles for sensitive operations, structured signaling for rate limits and abuse handling, and ways to reduce accidental over-fetching or global scraping. The goal is not to mandate a single policy, but to standardize how policy is expressed and communicated so clients can behave responsibly by default.

There are also ideas around structure and interoperability. These include typed relationship and reputation edges, scoped reputation signals, app and schema namespacing, cross-app objects, shared data surfaces, and deterministic client journals. The aim is to reduce fragmentation between apps and clients, and to make it easier to build multi-app experiences without each app inventing incompatible conventions.

At the relay level, several candidate directions explore clearer relay roles and topology. This includes relay policy declaration, retention and storage contracts, relay-to-relay replication, large object handling, cost and resource signaling, and audit-friendly receipts and attestations. The aim is to make relay behavior more legible and predictable, both for operators and for clients, especially as Nostr scales.

The list also touches broader application concerns such as moderation signals, community governance, portability of blocks and moderation decisions, dispute and evidence handling, markets and payments, receipts, escrow patterns, and graceful degradation during incidents. These are framed as primitives and signals, not application logic, so that different clients and communities can use them in their own way while still sharing a common language.

Taken together, this work sketches a version of Nostr where behavior is less dependent on undocumented assumptions, relay quirks, or client guesswork. The protocol remains simple at its core, but the edges are sharper. Failures are easier to reason about, state is easier to reconstruct, and different implementations are more likely to agree on what the data means.

If this direction holds, it becomes practical to build applications that need stronger guarantees without falling back to centralized infrastructure. That includes multi-client apps where profiles, settings, and lists reliably converge, communities with portable moderation and governance, marketplaces that can issue receipts and resolve disputes without a trusted backend, messaging and coordination tools that survive relay loss or network partitions, and systems that can prove authorship, delivery, or payment without relying on private databases. More broadly, it enables apps to assume less about relay behavior, to operate safely under partial failure, and to share data and trust signals across clients in a predictable way.

I am relatively new to writing and reviewing Nostr protocol specs, and this work is explicitly exploratory. The drafts here are intended as a starting point for discussion, not as final proposals. I am especially interested in feedback on overlap with existing NIPs or discussions, where these ideas may already be covered, where they might be too strict or too heavy, and where they do not fit the direction the Nostr ecosystem is moving.


<br><br>

## Table of contents

- [1. NIP-TIM-1: Strict Event Validation](#1-nip-tim-1-strict-event-validation)

<br><br>

## 1. NIP-TIM-1: Strict Event Validation

Link: [NIP-TIM-1: Strict Event Validation](nip-tim-1-strict-event-validation.md)

### Strict and uniform event validation

#### How it's related to 2WAY

2WAY is built around the idea that raw inbound data is never "application state" until it has passed a strict, consistent pipeline. The system boundary is enforced by shared managers and engines so that every consumer sees the same canonical shape and meaning. That is exactly the role this NIP plays for Nostr: it formalizes the "Incoming Engine boundary" concept, where parsing, canonicalization, and acceptance are centralized and deterministic, rather than scattered across feature code paths.

#### The NIP idea

Define a mandatory, ordered validation pipeline for all NIP-01 events, applied identically by clients and relays. The pipeline must specify exact stages, required checks, and hard failure outcomes. At minimum: JSON parse, type checks for required fields, tag structure checks, canonical serialization, id recomputation, signature verification, and basic invariants such as non-null fields, correct types, and bounded sizes when the relay advertises them. The NIP must define when an event becomes "valid", and it must require that once an event is considered valid, it is immutable and treated as a stable operation input. The NIP must also define how implementations should report failures in a structured way, without changing the event format.

This NIP started after reading discussions around network behavior and trying to understand why certain edge cases keep showing up across different Nostr apps, even when everyone is following NIP-01. The core issue seems to be that while NIP-01 defines the event format and cryptographic rules, it leaves a lot of room for interpretation in how events are validated, and in what order those checks are applied. The strict validation pipeline here is intended to run on clients, relays, or both, so they can make the same decisions about what is valid, safe to store, and safe to render.

In practice, different clients and relays make slightly different assumptions about when an event is valid, when it is safe to store, and when it is safe to render. Those small differences tend to leak upward into app logic, where they show up as duplicates, replay handling, inconsistent threading, or special-case code paths that are hard to reason about and easy to get wrong.

That discussion, especially callebtc's work on "Gossip mesh topology + source-based routing" (https://github.com/permissionlesstech/bitchat-android/pull/445), clarified the boundary between problems that belong to propagation and problems that belong to validation. A lot of effort is rightly going into making event delivery more robust under reordering, reconnection, and partial views of the network. At the same time, validation itself remains loosely defined and inconsistently enforced, which means application code often ends up compensating for malformed or ambiguously valid events after the fact.

This NIP is not meant to solve ordering, convergence, or propagation issues. Those are network-level problems, and they need network-level solutions. What this NIP tries to do is narrower: reduce the number of bad or ambiguous inputs that make those problems harder to handle downstream. By making validation stricter and uniform, fewer edge cases reach application logic, and fixes at the networking layer do not have to defensively account for inconsistent event shapes or partial validation.

This NIP does not introduce new event fields, new message types, or new relay behavior. Instead, it proposes a single, explicit validation pipeline for NIP-01 events, with clear stages and a fail-closed approach. The idea is that every event, whether inbound from the network or created locally, passes through the same sequence of checks before anything else happens.

The goal is not to make Nostr more complex, but to reduce accidental complexity. By tightening and unifying validation early, clients and relays can rely on a shared definition of what a "valid event" is, and keep the rest of their code simpler and more predictable, regardless of how events propagate through the network.

#### What this NIP solves in general

Nostr has a recurring class of bugs where "the protocol is simple" but implementations disagree on what "valid" means in practice. Some clients accept malformed tags and compensate later. Some relays enforce hidden constraints without describing them. Some code paths verify signatures early, others late. That inconsistency forces every app feature, threading, indexing, rendering, notifications, to become defensive code. This NIP stops that leak. When validation is strict and ordered, the ecosystem converges on one definition of "valid input", which reduces crashes, reduces duplicate handling inconsistencies, reduces weird replay behavior, and makes every downstream algorithm simpler because it can assume inputs are well-formed and verified.

#### Practical example of problems

A client receives an event where `tags` is present but contains an element that is not an array of strings, for example a nested object or a null. One client ignores it and continues. Another client tries to parse an `e` or `p` tag and fails a cast, breaking thread reconstruction. A relay might accept it and store it, then other clients repeatedly trip on it forever. Or the opposite: one relay rejects it but another accepts it, so users see inconsistent timelines depending on relay choice. With XX1, all implementations reject it at the same stage with the same meaning. The event never becomes storable or renderable, and the bug does not propagate.

#### What other NIPs this NIP relies on

* NIP-01 (event format, serialization and signature rules).
* NIP-TIM-2 (structured rejection reporting) if you want uniform failure codes, but NIP-TIM-1 can exist without it.
