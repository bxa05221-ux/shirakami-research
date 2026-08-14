# R0003 Test 01 — Multiform projection equivalence

status: experimental_contract
parent_contract: R0003

## Question

Can different surface languages represent the same projected Landscape State without changing its semantic identity?

## Canonical projected state

```text
relation:
  subject: Matome
  state: incomplete
  property: useful

verification:
  state: confirmed

provenance:
  actor_kind: human
  content_origin: human
```

## Projection A — YAML

```yaml
relation:
  subject: Matome
  state: incomplete
  property: useful
verification:
  state: confirmed
provenance:
  actor_kind: human
  content_origin: human
```

## Projection B — JSON

```json
{"relation":{"subject":"Matome","state":"incomplete","property":"useful"},"verification":{"state":"confirmed"},"provenance":{"actor_kind":"human","content_origin":"human"}}
```

## Projection C — Markdown

> Matome remains incomplete while being useful. The relation is confirmed and human-originated.

## Result

A and B preserve the structured relations explicitly.
C preserves the surface meaning but does not expose every metadata field directly.

Therefore, semantic equivalence does not require identical serialization. It requires that the projection preserve the relations required by the target use.

## Boundary

A surface representation may omit metadata only when the omitted information remains recoverable through the Runtime's lineage and projection context.

## Implication

Matome should be defined at the semantic layer before choosing a serialization language.

YAML is therefore an implementation choice, not a foundational requirement.

## Non-claim

This test establishes equivalence for one controlled state only. It does not prove general equivalence across all future Landscape State types.
