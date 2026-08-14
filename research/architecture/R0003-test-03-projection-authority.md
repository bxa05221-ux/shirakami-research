# R0003 Test 03 — Projection authority

status: experimental_contract
parent_contract: R0003

## Question

When YAML, JSON, Markdown, or another surface representation is edited, which representation has authority over the Landscape State?

## Test model

```text
Evidence / Transition Lineage
            ↓
     Semantic State
       ↙   ↓   ↘
    YAML JSON Markdown
```

## Rule

No projection is authoritative merely because it is machine-readable, human-readable, or stored in a particular backend.

The authoritative basis remains the verified Evidence and immutable transition lineage from which the semantic state is reconstructed.

## Edit cases

### Case A — Projection-only edit

A user changes wording in a YAML projection without producing a new Evidence or verified transition.

Result:
- semantic state does not automatically change;
- projection becomes divergent or stale;
- Runtime must detect or preserve the discrepancy.

### Case B — Human semantic revision

A user explicitly changes the underlying proposition through a new observed event.

Result:
- a new Evidence candidate is created;
- verification proceeds through the state machine;
- projections may then be regenerated from the new state.

### Case C — AI projection edit

AI modifies a YAML/JSON/Markdown projection to make it clearer.

Result:
- no Evidence change;
- no semantic-state authority is acquired;
- the modification remains a presentation operation unless separately verified.

## Result

The projection is a **view**, not a source of truth.

This prevents accidental authority inversion:

```text
Projection → State
```

is not the default direction.

The normal direction is:

```text
Evidence → State → Projection
```

## Implication

Multiple projections may coexist and may be regenerated independently. A backend storing a projection does not become the owner of the underlying Landscape State.

## Non-claim

This experiment does not define synchronization conflict policy for multiple human editors. It establishes only the authority boundary between semantic state and its projections.
