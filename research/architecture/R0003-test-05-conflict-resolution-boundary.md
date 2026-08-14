# R0003 Test 05 — Conflict resolution boundary

status: experimental_contract
parent_contract: R0003

## Question

When projections or verified Evidence disagree, where does conflict resolution belong?

## Conflict classes

### Projection divergence

Two projections derived from the same semantic state differ in wording, ordering, formatting, or completeness.

Result:
- do not treat either projection as authoritative;
- mark the projection as divergent or stale;
- regenerate from the semantic state when appropriate.

### Semantic conflict

Two verified Evidence lineages imply incompatible Landscape State values.

Result:
- Runtime records the conflict;
- Runtime does not silently choose a winner;
- Protocol determines the permitted coordination path;
- Human or explicitly authorized coordination may create a new transition.

### AI disagreement

An AI-generated hypothesis conflicts with current verified state.

Result:
- hypothesis remains AI-originated;
- current Evidence is not overwritten;
- the hypothesis may become a Counter-Evidence or observation target.

## Boundary

```text
Projection divergence
    → Runtime / Adapter handling

Semantic conflict
    → Protocol / Coordination

AI disagreement
    → Hypothesis / Counter-Evidence
```

## Result

Conflict is not a single generic error state. Its handling depends on the layer at which the disagreement occurs.

This preserves the authority boundary established by R0003 Test 03.

## Implication

Coordination is a first-class boundary between verified Landscape State and competing interpretations. Runtime should expose conflict state but should not invent semantic resolution.

## Non-claim

This does not define a distributed consensus algorithm or merge strategy. It defines only the responsibility boundary required by the current research model.
