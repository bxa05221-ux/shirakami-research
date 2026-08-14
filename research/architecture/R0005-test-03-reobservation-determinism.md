# R0005 Test 03 — Re-observation determinism

status: experimental_contract
parent_contract: R0005

## Question

When a rejected or unresolved transition is re-observed, can Runtime reproduce the previous observation without rewriting its history?

## Model

```text
Original Event
   ↓
Eligibility / Verification
   ↓
Recorded Observation
   ↓
New Observation
   ↓
Re-evaluation
   ↓
New Transition Event
```

## Case A — Same conditions

If the source, protocol version, required evidence, permission context, and relevant state are unchanged, re-observation should produce an equivalent evaluation result.

The new observation receives a new event identity. The previous result remains immutable.

## Case B — Changed conditions

If new human confirmation, new evidence, a protocol revision, or a changed conflict state exists, re-observation may produce a different result.

Example:

```text
E1: unresolved
E2: new human confirmation
E3: confirmed
```

E1 is not rewritten. E3 explains the new state.

## Case C — Projection changed only

If only a YAML/JSON/Markdown projection changed while the underlying Evidence lineage is unchanged, re-observation of the semantic state should remain equivalent. The projection is not treated as new semantic evidence.

## Result

Re-observation is a new observation event, not a mutation of the old event.

Determinism is therefore conditional on the same protocol, inputs, and relevant state—not on textual equality of projections.

## Implication

Runtime should preserve enough provenance and protocol-version information to explain why a repeated observation produced the same or a different result.

## Non-claim

This does not establish cryptographic determinism or identical implementation results across different Runtime versions. It establishes the conceptual requirement for reproducible evaluation under equivalent conditions.
