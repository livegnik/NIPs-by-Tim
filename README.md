



# NIPs by Tim

This repo contains [WIP] draft NIPs and notes that apply techniques focused on stronger guarantees around identity, permissions, ordering, and durable state across peers to Nostr. I want to see where I can help those approaches improve Nostr without changing its spirit.

The NIPs here are intended to span a wide range of Nostr topics. Some will be narrow and technical (event validation, tag structure, relay acceptance rules), while others will be broader (security boundaries, state and replay behavior, sync and reconciliation, moderation and permission signals, and the boundary between protocol guarantees and application policy). The common thread is making implicit assumptions explicit so implementations converge on the same behavior and security posture.

I am aiming to identify stable invariants, define clear validation and ordering pipelines, and document failure modes in a way that is testable and repeatable across clients and relays. The goal is not to centralize or over-specify, but to reduce ambiguity, prevent accidental divergence, and keep app logic smaller and more reliable.

I'm relatively new to Nostr and very open to feedback on this. The NIPs are meant as a starting point for discussion, not a final answer. I'm especially interested in hearing where it overlaps with existing work, where it might be too strict, or where it does not fit the direction Nostr is heading or other NIPs or discussions I may have missed or misinterpreted.



## 1. NIP-XX: Strict Event Validation

Link: [NIP-XX: Strict Event Validation](nip-xx-strict-event-validation.md)

### Strict and uniform event validation

This NIP grew out of trying to understand why certain edge cases keep showing up across different Nostr apps, even when everyone is "following NIP-01". The core issue seems to be that while NIP-01 defines the event format and cryptographic rules, it leaves a lot of room for interpretation in how events are validated, and in what order those checks are applied. The strict validation pipeline here is intended to run on clients, relays, or both, so they can make the same decisions about what is valid, safe to store, and safe to render.

In practice, different clients and relays make slightly different assumptions about when an event is valid, when it is safe to store, and when it is safe to render. Those small differences tend to leak upward into app logic, where they show up as duplicates, replay handling, inconsistent threading, or special-case code paths that are hard to reason about and easy to get wrong.

This repo started after reading discussions around network behavior, especially callebtc’s work on "Gossip mesh topology + source-based routing" (https://github.com/permissionlesstech/bitchat-android/pull/445), which clarified the boundary between problems that belong to propagation and problems that belong to validation. A lot of effort is rightly going into making event delivery more robust under reordering, reconnection, and partial views of the network. At the same time, validation itself remains loosely defined and inconsistently enforced, which means application code often ends up compensating for malformed or ambiguously valid events after the fact.

This NIP is not meant to solve ordering, convergence, or propagation issues. Those are network-level problems, and they need network-level solutions. What this NIP tries to do is narrower: reduce the number of bad or ambiguous inputs that make those problems harder to handle downstream. By making validation stricter and uniform, fewer edge cases reach application logic, and fixes at the networking layer do not have to defensively account for inconsistent event shapes or partial validation.

This NIP does not introduce new event fields, new message types, or new relay behavior. Instead, it proposes a single, explicit validation pipeline for NIP-01 events, with clear stages and clear failure modes. The idea is that every event, whether inbound from the network or created locally, passes through the same sequence of checks before anything else happens.

The goal is not to make Nostr more complex, but to reduce accidental complexity. By tightening and unifying validation early, clients and relays can rely on a shared definition of what a "valid event" is, and keep the rest of their code simpler and more predictable, regardless of how events propagate through the network.
