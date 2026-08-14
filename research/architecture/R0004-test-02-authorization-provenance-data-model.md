# R0004 Test 02 — Authorization, provenance, and semantic authority data model

status: experimental_contract
parent_contract: R0004

## Question

Can operation permission, event provenance, and semantic authority be represented as independent dimensions in one Runtime model?

## Candidate model

```text
Event
├─ event_id
├─ actor_id
├─ actor_kind
├─ content_origin
├─ operation
├─ permission_context
├─ verification_state
├─ semantic_effect
└─ lineage
```

## Dimension separation

### Permission context

Describes whether the actor was authorized to perform the operation.

### Provenance

Describes who produced the event and how the content originated.

### Verification state

Describes whether the event has crossed the Evidence boundary.

### Semantic effect

Describes whether the verified event contributes to the projected Landscape State.

## Test result

The dimensions can be kept independent without requiring the Runtime to infer semantic truth from permission.

Example:

```text
actor_kind: ai
content_origin: ai_generated
operation: write_projection
permission_context: authorized
verification_state: observed
semantic_effect: none
```

The AI may be fully authorized to write a projection while producing no verified semantic change.

## Implication

The Runtime data model should avoid a single overloaded field such as `trusted=true` or `authoritative=true`.

Trust, permission, provenance, verification, and semantic effect are different concepts and should not collapse into one boolean.

## Non-claim

This is a conceptual data-model test, not a final schema or implementation specification.
