# taudb

**taudb** is the home of **τ (tau)** — an immutable, append-only, event-sourced temporal database written in Zig.
This organisation contains the core database, supporting libraries, tooling, and experiments focused on building a principled temporal data system from first principles.



## What is Tau?

Tau is a temporal database built around a single invariant:

> **Data is never mutated — only extended through time.**

Rather than overwriting state, Tau stores *deltas* that are valid over explicit time ranges. This makes history, auditing, and point-in-time reconstruction intrinsic to the model instead of bolt-on features.
Tau is designed for domains where correctness over time matters:

- Time-series and sensor data
- Financial systems and audit trails
- Simulations and historical modelling
- Systems requiring deterministic replay



## Core Concepts

- **Tau** — an immutable delta valid for a specific time range
- **Schedule** — an ordered collection of related Taus
- **Frame** — a grouping of schedules that belong together
- **Lens** — a transformation that acts as both a view and a migration

These primitives allow Tau to represent evolving state without ever losing information.



## Why another database?

Traditional databases force trade-offs between:
- Write performance vs historical queries
- Storage efficiency vs duplication
- Flexibility vs auditability

Tau avoids these trade-offs by treating time as a first-class dimension and immutability as a hard constraint.



## Status

Tau is **early-stage and research-driven**.

The focus is on:
- Correctness and clear invariants
- Minimal, explicit abstractions
- Deterministic behaviour
- Long-term evolvability

APIs and on-disk formats may change.


## Philosophy

Tau is opinionated by design:

- Immutability over convenience
- Explicit time over implicit state
- Simple primitives over complex magic
