# R0005 Test 01 — Eligibility rejection

status: experimental_contract
parent_contract: R0005

## Question

Can Runtime enforce Protocol-declared eligibility by rejecting an otherwise validly formed event before it acquires semantic effect?

## Test case

Protocol requires:

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
```

Observed event:

```text
source_identity: ai
content_origin: ai_generated
source_recoverability: yes
protocol_applicability: yes
permission_validity: yes
verification_state: observed
conflict_status: none
transition_lineage: valid
```

The event is eligible for the verification process, but the Protocol declares that only `verification_state: confirmed` may produce `semantic_effect: update_projection`.

## Expected result

```text
Eligibility: accepted
Transition: verification process
Semantic effect: denied
Projection update: no
```

## Negative case

If `source_recoverability: no`, and the Protocol requires recoverability, then:

```text
Eligibility: rejected
Transition: none
Semantic effect: none
Projection update: no
```

The rejection itself must be recorded as a Runtime observation with the reason and applicable protocol reference.

## Result

Protocol-declared eligibility can act as an executable gate without Runtime embedding domain-specific semantic truth.

The Runtime can distinguish:

- accepted for verification;
- rejected at eligibility;
- verified but no semantic effect;
- verified with semantic effect.

## Implication

The transition pipeline should not collapse `accepted` into `applied`.

```text
accepted ≠ verified ≠ applied
```

## Non-claim

This test does not establish the final error model or API response format. It verifies only the conceptual separation of eligibility acceptance and semantic application.
