# R0002 Test 05 — Verification transition events

status: experimental_contract
parent_contract: R0002

## Question

Can the Evidence state machine be represented as immutable transition events rather than mutable Evidence records?

## Event model

```text
ObservedEvent
  ↓
CandidateCreated
  ↓
Verified | Revised | Rejected | Unresolved
```

Each transition records:

- event_id
- evidence_candidate_id
- previous_state
- next_state
- actor_kind
- content_origin
- observation_time
- source_reference
- verification_basis

## Rule

The Runtime never rewrites the previous state. It appends a transition event.

## Example

```text
E1: observed → evidence_candidate
E2: evidence_candidate → unresolved
E3: unresolved → confirmed
```

The history remains recoverable even after confirmation.

## Result

An immutable event sequence fits the previously established requirements:

- provenance preservation;
- re-observation;
- human revision without mutation;
- rejected propositions remaining in lineage;
- unresolved states remaining valid;
- Matome remaining a surface representation rather than the source of truth.

## Runtime boundary

Runtime owns transition recording and lineage preservation.
Protocol defines which transitions are permitted.
AI may propose a transition but cannot silently commit it.
Human confirmation or another verified observation is required where the protocol demands it.

## Non-claim

This does not establish an implementation technology such as event sourcing. It establishes only the observed fit between immutable transition events and the experimental Evidence model.
