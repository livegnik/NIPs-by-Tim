



# NIPs by Tim

This repo contains draft NIPs and notes as I work through how clients and relays can be more predictable and interoperable. I’m building out proposals that focus on Nostr’s real-world behavior: what should be validated, when to reject, how to represent intent unambiguously, and how to keep implementations aligned even when the network is messy.

The NIPs here are intended to span a wide range of Nostr topics. Some will be narrow and technical (event validation, tag structure, relay acceptance rules), while others will be broader (client expectations, sync and reconciliation, moderation and permission signals, and the boundary between protocol guarantees and application policy). The common thread is making the implicit parts of Nostr explicit, so different implementations behave the same way without relying on heuristics or hidden assumptions.

I’m aiming to identify stable invariants, define clear validation and ordering pipelines, and document failure modes in a way that is testable and repeatable across clients and relays. The goal is not to centralize or over-specify, but to reduce ambiguity, prevent accidental divergence, and keep app logic smaller and more reliable.

I'm relatively new to Nostr and very open to feedback on this. The NIPs are meant as a starting point for discussion, not a final answer. I'm especially interested in hearing where it overlaps with existing work, where it might be too strict, or where it does not fit the direction Nostr is heading or other NIPs or discussions I may have missed or misinterpreted.



1. ## NIP-XX: Strict Event Validation

### Strict and uniform event validation

This NIP grew out of trying to understand why certain edge cases keep showing up across different Nostr apps, even when everyone is "following NIP-01". The core issue seems to be that while NIP-01 defines the event format and cryptographic rules, it leaves a lot of room for interpretation in how events are validated, and in what order those checks are applied.

In practice, different clients and relays make slightly different assumptions about when an event is valid, when it is safe to store, and when it is safe to render. Those small differences tend to leak upward into app logic, where they show up as duplicates, replay handling, inconsistent threading, or special-case code paths that are hard to reason about and easy to get wrong.

Reading discussions around network behavior, especially callebtc’s work on "Gossip mesh topology + source-based routing" (https://github.com/permissionlesstech/bitchat-android/pull/445), helped clarify the boundary between problems that belong to propagation and problems that belong to validation. A lot of effort is rightly going into making event delivery more robust under reordering, reconnection, and partial views of the network. At the same time, validation itself remains loosely defined and inconsistently enforced, which means application code often ends up compensating for malformed or ambiguously valid events after the fact.

This NIP is not meant to solve ordering, convergence, or propagation issues. Those are network-level problems, and they need network-level solutions. What this NIP tries to do is narrower: reduce the number of bad or ambiguous inputs that make those problems harder to handle downstream. By making validation stricter and uniform, fewer edge cases reach application logic, and fixes at the networking layer do not have to defensively account for inconsistent event shapes or partial validation.

This NIP does not introduce new event fields, new message types, or new relay behavior. Instead, it proposes a single, explicit validation pipeline for NIP-01 events, with clear stages and clear failure modes. The idea is that every event, whether inbound from the network or created locally, passes through the same sequence of checks before anything else happens.

The goal is not to make Nostr more complex, but to reduce accidental complexity. By tightening and unifying validation early, clients and relays can rely on a shared definition of what a "valid event" is, and keep the rest of their code simpler and more predictable, regardless of how events propagate through the network.
