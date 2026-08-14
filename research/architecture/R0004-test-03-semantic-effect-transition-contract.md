# R0004 Test 03 — Semantic effect transition contract

status: experimental_contract
parent_contracts:
  - R0003
  - R0004

## Question

What is the minimum transition contract required before an observed event is allowed to affect the projected Landscape State?

## Proposed transition

```text
Observed Event
      ↓
Eligibility Check
      ↓
Verification State
      ↓
Semantic Effect
      ↓
State Projection
```

## Minimum transition fields

- `event_id`
- `actor_id`
- `content_origin`
- `previous_state`
- `next_state`
- `verification_basis`
- `semantic_effect`
- `source_reference`
- `protocol_id`
- `transition_time`

## Required rule

`semantic_effect` must never be inferred solely from:

- actor identity;
- write permission;
- projection location;
- AI confidence;
- textual similarity.

It must be authorized by the applicable Protocol and supported by the verification state.

## Example

```text
AI writes YAML
→ permission: authorized
→ verification: observed
→ semantic_effect: none
```

After explicit human confirmation:

```text
Human confirmation
→ verification: confirmed
→ semantic_effect: update
→ new projection generated
```

## Result

The semantic effect is a controlled consequence of a verified transition, not a side effect of writing to a backend.

## Runtime boundary

Runtime evaluates and records the transition contract, preserves lineage, and materializes the resulting projection. It does not invent semantic effects outside the protocol.

## Non-claim

This is the minimum tested conceptual contract, not a final API schema.
