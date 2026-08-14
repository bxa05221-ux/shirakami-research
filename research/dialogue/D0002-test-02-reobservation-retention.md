# D0002 Test 02 — Re-observation retention boundary

status: experiment
contract: D0002
counter_evidence: CE0002

## Test question

What is the minimum source material that must remain recoverable after Matome compression so that a later observation can reinterpret an earlier transition?

## Candidate retention levels

### R0 — Matome only

Keeps the current surface representation and discards source dialogue.

### R1 — Matome + Evidence identity

Keeps the surface plus a pointer to the source Evidence.

### R2 — Matome + Evidence identity + Delta identity

Keeps source Evidence and the observed transition reference.

### R3 — Matome + recoverable source segment + lineage

Keeps the compressed surface, lineage, and enough original source material to re-observe the disputed transition.

## Result

R0 is insufficient for re-observation because the source cannot be recovered.

R1 preserves provenance but does not guarantee that the underlying transition can be reinterpreted.

R2 preserves the transition reference but still may lack the contextual material needed to resolve a later question.

R3 is the first tested level that explicitly supports later re-observation without requiring permanent storage of the entire conversation.

## Observation

The retention boundary is therefore better described as **recoverable re-observation context**, not transcript completeness.

## Implication for Matome

Matome may remain small and representation-language independent. The Runtime or an adjacent storage layer must preserve enough source material to reconstruct the Evidence/Delta relationship when later observation requires it.

## Non-claim

R3 is not established as a universal storage minimum. It is the first sufficient level in this experiment.
