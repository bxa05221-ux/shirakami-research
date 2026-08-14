# R0004 Test 01 — Authority versus semantic truth

status: experimental_contract
parent_contract: R0004

## Question

Can authorization to modify a Landscape be kept separate from authority to determine semantic truth?

## Test cases

### Case A — Authorized editor

An actor has permission to modify a projection or initiate a transition.

Result:
- permission authorizes the operation;
- it does not make the actor's interpretation true;
- the resulting event remains subject to the protocol's verification rules.

### Case B — Human owner disagrees with authorized editor

The owner and an authorized collaborator provide incompatible propositions.

Result:
- both retain independent provenance;
- neither wins merely because of edit permission;
- the conflict enters the coordination path defined by protocol.

### Case C — AI has write capability

An AI adapter is technically capable of modifying a projection.

Result:
- technical capability is not semantic authority;
- the AI-originated change cannot silently become Human Evidence;
- permission and verification remain separate dimensions.

## Result

Three concepts must remain distinct:

```text
Permission
  = may perform an operation

Provenance
  = who produced the event/content

Verification / Semantic Authority
  = whether the proposition may affect the verified Landscape State
```

## Implication

A Runtime permission model must not be reused as a truth model.

An administrator may be allowed to repair infrastructure, regenerate projections, or initiate coordination without being granted automatic authority to redefine another actor's verified Landscape.

## Non-claim

This does not define a complete access-control system or governance model. It establishes only the separation required to prevent permission escalation from becoming semantic truth escalation.
