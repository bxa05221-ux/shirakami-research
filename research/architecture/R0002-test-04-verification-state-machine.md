# R0002 Test 04 — Verification state machine

status: experimental_contract
parent_contract: R0002

## State model

```text
observed
  ↓
evidence_candidate
  ├→ confirmed
  ├→ revised
  ├→ rejected
  └→ unresolved
```

## Semantics

- `observed`: a source event has been recorded but its Evidence boundary is not yet established.
- `evidence_candidate`: the content is attributable to a source actor and is eligible for verification.
- `confirmed`: the proposition has been explicitly confirmed without unresolved ambiguity.
- `revised`: the human has changed or qualified the proposition; the earlier candidate remains immutable and a new candidate is created.
- `rejected`: the proposition is explicitly denied; the rejected candidate remains in lineage but is not promoted to Evidence.
- `unresolved`: available interaction does not establish whether the proposition should cross the Evidence boundary.

## Transition rules

1. No transition may rewrite an earlier source event.
2. AI confirmation cannot promote an AI-originated proposition to human Evidence.
3. Human acknowledgement without a distinguishable proposition does not imply `confirmed`.
4. Human revision creates a new Evidence candidate rather than mutating the previous candidate.
5. Rejection preserves the rejected proposition as lineage information but prevents promotion.
6. `unresolved` is a valid terminal state until new observation occurs.

## Runtime responsibility

Runtime records state transitions and preserves lineage. It does not decide semantic truth beyond the explicit verification rules supplied by the protocol.

## Research implication

Evidence creation is best modeled as a controlled state transition over an observed source event, not as a static label attached to a speaker.

## Non-claim

This is an experimental state model. It is not yet a finalized Shirakami Runtime contract.
