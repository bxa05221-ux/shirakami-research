# R0005 Test 02 — Negative observation recording

status: experimental_contract
parent_contract: R0005

## Question

Should rejected and unresolved events be retained as observations even when they produce no semantic effect?

## Test model

```text
Observed Event
   ↓
Eligibility
   ├─ rejected
   └─ accepted
        ↓
    Verification
        ├─ unresolved
        ├─ rejected
        └─ confirmed
```

Every branch produces a recorded observation.

## Rejected eligibility

```text
result: rejected
semantic_effect: none
projection_effect: none
reason: missing_required_source_recoverability
```

The event remains available for audit and re-observation.

## Unresolved verification

```text
result: unresolved
semantic_effect: none
projection_effect: none
reason: insufficient_human_confirmation
```

The unresolved state is retained until a new observation permits another transition.

## Confirmed transition

```text
result: confirmed
semantic_effect: protocol_defined
projection_effect: derived
```

The earlier rejected or unresolved observations remain unchanged in lineage.

## Result

Negative outcomes are not absence of data. They are observations about the state of the transition process.

This means Runtime Evidence should distinguish:

- observation of an event;
- eligibility result;
- verification result;
- semantic effect.

## Implication

A failed transition should not disappear merely because it produced no Landscape State change.

This preserves diagnostic history without granting negative observations semantic authority they do not possess.

## Non-claim

This does not define retention duration, privacy policy, or storage format. It establishes only that negative transition outcomes are observable Runtime events and should remain distinguishable from successful semantic changes.
