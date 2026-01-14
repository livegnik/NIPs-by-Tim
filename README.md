



# NIPs by Tim

This repo contains a set of draft NIPs and exploratory notes, all work in progress. Nothing here is adopted or final. Together they explore how Nostr could gain stronger and more predictable behavior around identity, permissions, ordering, privacy, and durable state across peers, without changing Nostr’s core model or culture. The starting point for this work is a set of ideas I previously developed for [2WAY](https://github.com/livegnik/2way-poc-design). In 2WAY, these ideas are enforced by design through strict boundaries, ordered pipelines, and deterministic rules, so that different implementations reliably arrive at the same result.

Here, those same ideas are used as guidance rather than as something to copy directly. Instead of importing 2WAY as a system, I am using it as a source of constraints and questions. For each idea, the goal is to ask how it could make sense inside Nostr’s existing event model and relay ecosystem. That means translating concepts like explicit ingress pipelines, deterministic handling of replaceable events, or clear deletion and visibility rules into proposed Nostr terms such as event types, tags, relay behavior, client expectations, and well-defined failure cases.

A central theme throughout this work is making implicit assumptions explicit. Today, many parts of Nostr rely on unwritten conventions or client-specific heuristics. Different relays reject or accept events differently. Clients often guess how to page, replay, or merge data from multiple relays. These drafts aim to turn those informal expectations into documented, testable rules, so implementations can converge on the same behavior more often and with less guesswork.

Several of the proposed areas focus on convergence and correctness. These include stricter validation boundaries, clearer ordering of relay ingress and egress stages, idempotent replay behavior, deterministic rebuild of client state, and stable merge rules when events arrive from different relays in different orders. The intent is not to make Nostr rigid, but to ensure that two compliant clients, even when connected to different relay sets, are more likely to reconstruct the same logical state from the same data.

Other areas focus on safety, privacy, and abuse resistance. These ideas explore clearer authorization and capability patterns, safer ways to use and delegate keys, explicit privacy profiles for sensitive operations, and more structured signaling for rate limits and abuse handling. Rather than enforcing a single global policy, the goal is to standardize how policies are expressed and communicated, so clients can behave responsibly by default and users get fewer surprises.

Security model considerations are also in scope. This includes clarifying the threat model and relay/client responsibilities, and exploring adaptive anti-abuse controls such as dynamic PoW difficulty via client puzzles rather than a single static target. The aim is to make resource costs and expectations explicit, so relays can adjust to load while clients can anticipate and comply with published constraints.

There are also ideas aimed at improving structure and interoperability. These include typed relationship and reputation edges, scoped reputation signals, app and schema namespacing, cross-app objects, shared data surfaces, and deterministic client journals. By giving these patterns a clearer shape, apps can interoperate more easily, and developers can build multi-app experiences without inventing incompatible conventions for each project.

At the relay level, several candidate directions explore how to make relay behavior easier to understand and reason about. This includes clearer relay policy declarations, retention and storage contracts, relay-to-relay replication, handling of large objects, cost and resource signaling, and audit-friendly receipts and attestations. The aim is to reduce surprises for both relay operators and clients, especially as Nostr grows and becomes more diverse.

This repo also touches broader application concerns such as moderation signals, community governance, portability of blocks and moderation decisions, dispute and evidence handling, markets and payments, receipts, escrow patterns, and graceful degradation during incidents. These are treated as shared primitives and signals rather than hard-coded application logic, so different communities and clients can use them in ways that fit their own values while still speaking a common language.

Throughout the repo, there is an important distinction between what these NIPs try to achieve and what they cannot fully guarantee. Even with clearer rules and stronger conventions, Nostr remains a loosely coordinated ecosystem of independent relays and clients. These drafts can reduce ambiguity and fragmentation, but they cannot enforce outcomes in the same way a single integrated system can. That difference is intentional. The goal here is to explore how far Nostr can be strengthened using shared rules and conventions, and to better understand which guarantees can realistically be expressed at the protocol level within Nostr’s existing design.

If this direction holds, it becomes much easier to build apps on Nostr that normally require a central server. Profiles, settings, and lists can converge more reliably across clients. Communities can carry their rules and moderation with them instead of tying them to one app. Markets can show payments, receipts, and dispute outcomes without relying on a private backend. Messaging and coordination tools can keep working when relays go down or networks split. In general, apps can assume less, recover state more safely, and share data and trust signals in ways that stay consistent and understandable across clients.

I am relatively new to writing and reviewing Nostr protocol specs, and this work is explicitly exploratory. These drafts are meant to start a conversation, not to present final answers or existing standards. I am especially interested in feedback on overlap with existing NIPs or discussions, where these ideas may already be covered, where they might be too strict or too heavy, and where they do not fit the direction the Nostr ecosystem is moving.


<br><br>

## Table of contents

- [1. NIP-TIM-1: Strict Event Validation](#1-nip-tim-1-strict-event-validation)

<br><br>

## 1. NIP-TIM-1: Strict Event Validation

NIP draft: [NIP-TIM-1: Strict Event Validation](nip-tim-1-strict-event-validation.md)

NIP proposal: https://github.com/nostr-protocol/nips/issues/2188

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

