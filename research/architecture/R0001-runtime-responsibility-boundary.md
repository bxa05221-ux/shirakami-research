# R0001 — Runtime responsibility boundary for Matome and re-observation

status: research_candidate

## Observed baseline

The Shirakami OS Foundation currently defines the Runtime as an architectural boundary and describes the project as Landscape First. The public repository explicitly separates Foundation specifications from research notes and implementation details.

## Derived boundary

The Runtime should be responsible for preserving the integrity of the relationship between:

- Human-originated Evidence
- observed Delta
- Matome surface representation
- recoverable source context
- lineage
- verification state
- AI-generated hypotheses

## Runtime responsibilities

1. Preserve source Evidence identity and immutability.
2. Preserve Delta identity and its relationship to Evidence.
3. Allow Matome to be represented in multiple surface languages.
4. Preserve enough recoverable source context for later re-observation.
5. Keep AI-generated hypotheses distinct from Evidence.
6. Permit a Matome surface to remain smaller than its underlying Evidence context.
7. Expose sufficient lineage for an Adapter or observer to reconstruct provenance.

## Explicit non-responsibilities

The Runtime should not decide:

- what a human statement ultimately means;
- whether an AI hypothesis is true merely because it is coherent;
- which representation language is the canonical Matome language;
- which unresolved question must be resolved.

## Candidate architecture

Landscape
→ Evidence
→ Delta
→ Runtime boundary
→ Matome Surface / Hypothesis / Re-observation
→ Adapter

## Research status

This is not yet a Foundation specification. It is a research candidate derived from D0002 and MP0001 experiments.
