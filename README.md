



# NIPs by Tim

This repo contains draft NIPs [work in progress] that apply techniques focused on stronger guarantees around identity, permissions, ordering, and durable state across peers to Nostr. The work is grounded in what I have already designed for 2WAY. 2WAY defines strict boundaries, ordered pipelines, and deterministic outcomes so that every consumer sees the same canonical shape and meaning. With Nostr already in motion, I am taking slices of that design and mapping them to Nostr where they seem relevant, actionable, and clearly beneficial, to then write NIPs that translate those ideas into Nostr's event model and relay ecosystem without changing Nostr's spirit.

In practice, that means each NIP starts from a concrete 2WAY concept (for example, an explicit ingress pipeline, deterministic replaceable resolution, or structured policy feedback) and then asks how it should look in Nostr terms: which event types, which validation stages, what relay behavior, and what client guarantees. The goal is not to import 2WAY wholesale, but to use it as a source of constraints and invariants that help Nostr implementations converge on the same behavior. These drafts focus on making implicit assumptions explicit, turning hidden or ad-hoc behavior into testable rules, and drawing a cleaner boundary between protocol guarantees and application policy.

This work is organized as a map of candidate NIPs grouped by area. For each area, it translates a specific 2WAY concept into Nostr terms and ties it to a concrete protocol or client/relay behavior problem. That includes: strict validation boundaries; ordered ingress and egress pipelines; idempotent replay and deterministic state rebuilds; explicit lifecycle and visibility semantics for deletion and retention; scoped discovery and bounded propagation; explicit authorization and capability grants; consistent privacy and metadata-hiding profiles; typed relationship and reputation edges; relay topology and storage contracts; structured receipts and auditability; deterministic merge rules for multi-relay views; and clear policy vs invalidity signaling.

The NIPs here are intended to span a wide range of Nostr topics. Some will be narrow and technical (event validation, tag structure, relay acceptance rules), while others will be broader (security boundaries, state and replay behavior, sync and reconciliation, moderation and permission signals, and the boundary between protocol guarantees and application policy). The common thread is making implicit assumptions explicit so implementations converge on the same behavior and security posture, while keeping the protocol flexible and the client surface simple.

I am aiming to identify stable invariants, define clear validation and ordering pipelines, and document failure modes in a way that is testable and repeatable across clients and relays. The goal is not to centralize or over-specify, but to reduce ambiguity, prevent accidental divergence, and keep app logic smaller and more reliable.

I'm relatively new to the Nostr protocol specs and very open to feedback on this. The NIPs are meant as a starting point for discussion, not a final answer. I'm especially interested in hearing where it overlaps with existing work, where it might be too strict, or where it does not fit the direction Nostr is heading or other NIPs or discussions I may have missed or misinterpreted.

<br><br>

## Table of contents

- [1. NIP-XX1: Strict Event Validation](#xx1-nip-xx1-strict-event-validation)

<br><br>

## 1. NIP-XX: Strict Event Validation

Link: [NIP-XX1: Strict Event Validation](nip-xx1-strict-event-validation.md)

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
* XX2 (structured rejection reporting) if you want uniform failure codes, but XX1 can exist without it.
