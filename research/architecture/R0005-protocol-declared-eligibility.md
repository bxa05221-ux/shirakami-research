# R0005 — Protocol-declared Eligibility

status: experimental_contract
parent_contract: R0004-test-04

## Question

Can Eligibility Checks be declared by Protocol so that Runtime enforces the contract without embedding domain theory?

## Proposed separation

```text
Protocol
  ├─ eligibility requirements
  ├─ permitted transitions
  ├─ verification rules
  └─ semantic-effect rules

Runtime
  ├─ observe event
  ├─ evaluate declared requirements
  ├─ record result
  ├─ execute permitted transition
  └─ preserve lineage
```

## Example protocol declaration

```yaml
eligibility:
  require:
    - source_identity
    - content_origin
    - source_recoverability
    - protocol_applicability
    - permission_validity
    - verification_state
    - conflict_status
    - transition_lineage

transitions:
  - from: evidence_candidate
    to: confirmed
    when:
      verification_state: confirmed

semantic_effect:
  confirmed: update_projection
  unresolved: none
  rejected: none
```

## Result

The Runtime can treat these entries as executable contract metadata rather than hard-coding the meaning of each domain-specific protocol.

The Runtime therefore remains a generic transition engine while Protocol carries the rules that determine eligibility and semantic effect.

## Boundary

Protocol may declare:
- what must be present;
- which states are permitted;
- which transitions are legal;
- what semantic effect follows a verified transition.

Protocol should not silently redefine immutable Evidence already recorded by the Runtime.

## Implication

This preserves the Shirakami OS principle that Protocol is separate from Runtime while allowing Protocols to become operational rather than merely descriptive.

## Non-claim

This is not a finalized YAML schema. The syntax is illustrative and remains subject to research validation.
