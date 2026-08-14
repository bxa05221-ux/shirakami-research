# R0003 Test 04 — Projection conflict handling

status: experimental_contract
parent_contract: R0003

## Question

What should Runtime do when multiple projections of the same Landscape State disagree?

## Test cases

### Case A — Textual divergence only

YAML and JSON express the same semantic relation using different wording or ordering.

Result:
- no semantic conflict;
- projections may coexist;
- normalization can identify equivalent state.

### Case B — Semantic divergence without new Evidence

YAML says `state: incomplete`, while JSON says `state: complete`, but neither projection is backed by a new verified transition.

Result:
- neither projection gains authority;
- Runtime marks the projections divergent;
- Semantic State remains reconstructed from Evidence/Transition lineage.

### Case C — Verified human revision exists

A new Human Evidence event establishes `state: complete`.

Result:
- the new verified transition changes the Semantic State;
- stale projections become outdated views;
- projections may be regenerated.

### Case D — Conflicting verified transitions

Two independently verified transitions assert incompatible states.

Result:
- Runtime must not select one by timestamp, backend, format, or AI preference alone;
- conflict becomes an explicit Landscape condition;
- resolution requires a protocol-defined coordination or human decision step.

## Result

Projection conflict and Landscape conflict are different classes.

```text
Projection conflict
  = views disagree
  = resolve by re-projection / divergence handling

Landscape conflict
  = verified evidence disagrees
  = cannot be solved by rewriting a view
```

## Implication

The Runtime needs a `divergent` or equivalent projection status, but must not turn projection divergence into Evidence or silently repair it.

For verified semantic conflict, Runtime records the conflict and invokes the protocol-defined coordination path.

## Non-claim

This test does not define a final conflict-resolution algorithm. It establishes only that projection divergence must not acquire semantic authority and verified Evidence conflict must remain observable.
