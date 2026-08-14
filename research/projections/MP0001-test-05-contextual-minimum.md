# MP0001 Test 05 — Contextual minimum

status: experiment
contract: MP0001
source_evidence: E0002-matome-incompleteness-useful.md
source_delta: D0001

## Test relation

Base relation:

> Incomplete Matome was useful.

The experiment asks whether the relation alone remains semantically stable when the subject, time, or condition changes.

## Variants

### R0 — relation only

Incomplete Matome was useful.

### R1 — subject removed

It was useful.

### R2 — temporal context removed

Matome was useful.

### R3 — condition/context removed

Incomplete Matome was useful.

### R4 — relation with explicit context

For this participant, during the design/revision period, incomplete Matome was useful because it allowed the representation to remain open to later clarification.

## Observation

R1 loses the subject and becomes ambiguous.
R2 can remain readable in this isolated case, but loses temporal lineage.
R3 is equivalent to R0 for this specific test because the original relation does not contain a separately evidenced condition.
R4 contains an interpretation (“because...”) that is not itself established by the current Evidence/Delta pair and therefore must not be promoted without separate evidence.

## Result

The tested minimum is not a universal tuple of subject + time + condition.

The stronger result is:

> A contextual field is required when removing it changes the identity, scope, or falsifiability of the observed relation.

## Implication

The Matome surface should be schema-light. Context should be carried only when it is semantically necessary for the relation being represented.

This supports a variable-width semantic representation rather than a fixed YAML schema.

## Non-claim

No universal semantic tuple has been established. Further Evidence/Delta pairs are required.
