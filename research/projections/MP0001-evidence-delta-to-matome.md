# MP0001 — Evidence/Delta to Matome projection boundary

status: experimental_contract

## Purpose

Define the smallest experimentally testable boundary for producing a Matome representation from an Evidence and its observed Delta.

## Input

- source_evidence: immutable Evidence reference
- delta: observed change reference
- representation_language: implementation detail, not part of Evidence

## Output

- matome_candidate: a derived representation
- lineage: references to source_evidence and delta
- omissions: information intentionally not represented
- unresolved: questions or ambiguity retained rather than resolved

## Invariants

1. Source Evidence is never rewritten.
2. Delta is not converted into an asserted cause unless separately evidenced.
3. Matome Candidate cannot become Evidence solely by generation.
4. Representation language may change without changing the source Evidence identity.
5. Unresolved ambiguity must remain explicitly representable.

## Verification target

Compare multiple Matome candidates generated from the same Evidence/Delta pair using different representation languages and determine whether the same observable relations and lineage survive.

## Status

This is an experimental contract, not a finalized Runtime specification.
