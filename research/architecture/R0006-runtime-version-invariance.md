# R0006 — Runtime Version Invariance

status: experimental_contract
parent_contracts:
  - R0003
  - R0005

## Question

When the Runtime implementation changes, what must remain stable for the same Landscape to remain the same Landscape?

## Candidate invariant

Runtime version is not part of the semantic identity of a Landscape State.

The invariant basis is:

```text
Landscape identity
    +
Evidence lineage
    +
Protocol identity/version
    +
Semantic State
```

The Runtime is the execution mechanism that interprets the Protocol and reconstructs the projection. A Runtime upgrade must not silently rewrite historical Evidence or alter its provenance.

## Case A — Equivalent Runtime

Runtime v1 and Runtime v2 interpret the same Protocol version and Evidence lineage and produce the same semantic state.

Result:

```text
same Landscape State
```

The projection may differ in formatting without changing semantic identity.

## Case B — Runtime behavior changes

Runtime v2 produces a different evaluation from the same historical inputs.

Result:

- historical Evidence remains immutable;
- the difference is recorded as a Runtime-version-dependent observation;
- the semantic state must not be silently rewritten;
- reconciliation requires an explicit protocol/version transition or verification path.

## Case C — Protocol version changes

A new Protocol version intentionally changes the permitted transition rules.

Result:

The change is semantic infrastructure, not merely a Runtime implementation change. The new Protocol version must be recorded in the resulting transition lineage.

## Result

The ability to replace Runtime implementations without destroying Landscape continuity depends on treating Runtime version as execution metadata rather than semantic identity.

## Implication

The phrase "AI can be replaced" can be generalized:

```text
AI implementation may change.
Runtime implementation may change.
Projection format may change.

Landscape continuity is preserved by Evidence + Protocol lineage.
```

## Non-claim

This does not prove cross-version deterministic execution. It defines the invariants that must be preserved if Shirakami OS is to support Runtime replacement without semantic history loss.
