# R0004 Test 04 — Eligibility Check Contract

status: experimental_contract
parent_contract: R0004-test-03

## Question

What must Runtime establish before an observed event is eligible to produce a semantic effect on Landscape State?

## Minimum eligibility checks

```text
1. Source identity
2. Content origin
3. Source recoverability
4. Protocol applicability
5. Permission validity
6. Verification state
7. Conflict status
8. Transition lineage
```

## Important separation

Eligibility is not semantic truth.

The Runtime asks whether an event is **eligible to enter the transition process**. It does not ask whether the proposition is universally true.

## Example: AI projection write

```text
source identity       = AI
content origin        = AI-generated
source recoverability = yes
protocol applicable   = yes
permission valid      = yes
verification state    = observed
conflict status       = none
lineage               = valid

Eligibility: yes
Semantic effect: none
```

The event may be recorded and may proceed through verification, but it does not automatically change the Landscape State.

## Example: human confirmed revision

```text
source identity       = human
content origin        = human
source recoverability = yes
protocol applicable   = yes
permission valid      = yes
verification state    = confirmed
conflict status       = resolved
lineage               = valid

Eligibility: yes
Semantic effect: protocol-defined update
```

## Example: unverifiable source

If the source cannot be recovered sufficiently for re-observation, the event may remain recorded but cannot cross a protocol-defined Evidence boundary that requires recoverability.

## Result

Eligibility is a **gate into controlled transition**, not a truth oracle.

This preserves the previously established boundaries between permission, provenance, verification, semantic effect, and projection.

## Runtime responsibility

Runtime performs or records the eligibility checks required by the active Protocol and preserves the reasons for acceptance, rejection, or unresolved status.

## Non-claim

The exact checks and thresholds remain Protocol-specific. This document defines the minimum conceptual dimensions, not a universal validation algorithm.
