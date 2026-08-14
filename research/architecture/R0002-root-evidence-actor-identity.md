# R0002 — Root Evidence and actor identity

status: experimental_contract
question: Q0001

## Root premise

The system begins from a minimal Evidence condition: an observed participant exists and is classified as either human or AI.

This classification is not a judgment of capability or value. It identifies the source class of an Evidence event.

## Proposed root identity

- actor_id
- actor_kind: human | ai
- evidence_id
- observation_time
- source_reference
- verification_state

## Human-first interpretation

For a user Landscape, the root participant is explicitly represented as `human` when the system has verified that the participant is a human user.

AI-generated content is represented as `ai` and must not silently inherit human-origin Evidence identity.

## Counter-evidence requirement

Where actor identity is uncertain, the Runtime must preserve the uncertainty rather than infer `human` or `ai` from content style alone.

A corresponding counter-evidence or verification event may later change the classification state.

## Implication

Identity is part of Evidence provenance, not part of the Matome surface by default.

Matome may omit actor identity when the identity is not necessary for the surface meaning, while the Runtime retains it as lineage metadata.

## Non-claim

This contract does not define authentication technology or prove biological/human identity. It defines the provenance category required by the research model.

## Next observation target

Test whether separating `actor_kind` from surface representation prevents AI-generated inference from being promoted to human Evidence during dialogue.
