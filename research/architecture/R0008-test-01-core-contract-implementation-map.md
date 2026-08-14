# R0008 Test 01 — Core Contract implementation map

status: experimental_contract
parent_contract: R0008

## Purpose

Translate the consolidated Core Contract into the minimum implementation boundaries without defining a final schema prematurely.

## Boundary map

```text
Event
  ↓
Observation
  ↓
Eligibility
  ↓
Verification
  ↓
Transition
  ↓
Semantic Effect
  ↓
Landscape State
  ↓
Projection
  ↓
Adapter
```

## Minimum responsibilities

### Event

Carries an immutable event identity, actor/provenance information, source reference, operation context, and lineage reference.

### Observation

Records what Runtime observed and the evaluation outcome. Rejected and unresolved outcomes remain observable.

### Eligibility

Evaluates Protocol-declared requirements. Eligibility acceptance does not imply verification or semantic application.

### Verification

Carries the Protocol-defined status required before a semantic effect can occur.

### Transition

Records the controlled state change, including previous state, next state, Protocol version, verification basis, and transition time.

### Semantic Effect

Represents the Protocol-authorized consequence of a verified transition. It is not inferred from permission or projection writes.

### Landscape State

Represents the semantic state reconstructed from Evidence and Protocol lineage.

### Projection

Represents a derived form of Landscape State. Projection divergence must not alter semantic state.

### Adapter

Translates Landscape State and projections to external backends without becoming semantic authority.

## Test result

The Core Contract can be decomposed into implementation boundaries without introducing a semantic judge inside Runtime.

## Key invariant

```text
Backend Write ≠ Semantic Transition
Projection ≠ Source of Truth
Permission ≠ Verification
Runtime ≠ Semantic Authority
```

## Next implementation target

Define the smallest concrete Event/Evidence/State/Transition interface and execute one end-to-end test through an existing Adapter.

## Non-claim

This map is not a final API or database schema. It is an implementation boundary map derived from R0008.
