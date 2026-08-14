# R0003 Test 02 — Round-trip projection identity

status: experimental_contract
parent_contract: R0003

## Question

If a Landscape State is projected into different surface languages and parsed back, does the reconstructed semantic state retain the same identity?

## Test

Canonical semantic state:

```text
relation(subject=Matome, state=incomplete, property=useful)
verification(state=confirmed)
provenance(actor_kind=human, content_origin=human)
```

Projection paths:

```text
Semantic State → YAML → Semantic State
Semantic State → JSON → Semantic State
Semantic State → Markdown → Semantic State
```

## Result

YAML and JSON can preserve the complete tested structure and therefore support deterministic round-trip reconstruction.

Markdown can preserve the human-readable relation, but its reconstruction is dependent on an interpretation layer and therefore cannot guarantee lossless recovery of all metadata.

## Observation

Projection identity is not the same as textual identity.

A round-trip is lossless only when the projection contains, or has recoverable access to, every semantic field required for the target State identity.

## Consequence

A serialization format should not be treated as canonical merely because it is machine-readable.

The canonical object is the semantic Landscape State plus its lineage. Surface formats are replaceable projections.

## Non-claim

This does not establish that Markdown is unsuitable. It establishes only that Markdown alone is insufficient for deterministic reconstruction of the tested full state.
