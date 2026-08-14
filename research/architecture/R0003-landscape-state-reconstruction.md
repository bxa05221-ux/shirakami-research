# R0003 — Landscape State Reconstruction

status: experimental_contract
parent_contract: R0002

## Question

If Evidence is represented as immutable transition events, how is the current Landscape State reconstructed without making the state itself the source of truth?

## Proposed model

```text
Immutable Evidence Events
        ↓
   ordered transition log
        ↓
    State Projection
        ↓
 Current Landscape State
```

## Rules

1. Evidence events are immutable.
2. Current Landscape State is a projection derived from applicable events.
3. A projection may be rebuilt from retained source and transition lineage.
4. Rebuilding a projection must not modify the underlying Evidence events.
5. Matome is one possible presentation of the projected state; it is not the state itself.
6. Different surface representations may project the same underlying state.
7. Unresolved and rejected transitions remain part of lineage even when they do not contribute to the active state.

## Example

```text
E1: human proposition observed
E2: candidate created
E3: candidate unresolved
E4: human revision observed
E5: revised candidate confirmed
```

The active Landscape State is derived from E4/E5, while E1–E3 remain recoverable historical lineage.

## Result

The current state can be treated as a **projection**, not a mutable master record.

This separates:

- Evidence history;
- verification transitions;
- current Landscape State;
- Matome surface representation.

## Runtime responsibility

Runtime may materialize and cache the current projection for efficient use, but the projection is disposable and reconstructible.

## Implication for Matome language

Because Matome is downstream of the state projection, its serialization language can vary independently from the underlying Evidence model.

YAML, JSON, Markdown, or another representation can all be projections of the same Landscape State if they preserve the required semantic relations.

## Non-claim

This experiment does not establish a specific database, event-sourcing implementation, or serialization language. It establishes only the conceptual separation between immutable evidence history and derived current state.
