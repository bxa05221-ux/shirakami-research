# R0007 — Protocol Migration Contract

status: experimental_contract
parent_contract: R0006

## Question

When a Protocol changes from v1 to v2, how can Landscape continuity be preserved without rewriting historical Evidence?

## Principle

A Protocol migration is itself a new transition. It does not rewrite the historical Protocol interpretation under which earlier Evidence was produced.

```text
Historical Evidence
      ↓
Protocol v1 interpretation
      ↓
Migration transition
      ↓
Protocol v2 interpretation
      ↓
New projection
```

## Migration requirements

A migration must preserve:

- Evidence identity;
- Evidence provenance;
- original Protocol identity/version;
- original transition lineage;
- migration source and target Protocol versions;
- migration rationale or declared rule;
- resulting verification state;
- semantic effect of the migration.

## Case A — Semantically equivalent Protocol update

Protocol v2 changes syntax or execution details but preserves the tested semantic rules.

Result:

```text
same Evidence lineage
same semantic State
new Protocol metadata
new projection may be generated
```

## Case B — Semantic Protocol change

Protocol v2 intentionally changes the rules that determine eligibility, verification, or semantic effect.

Result:

```text
old interpretation remains recoverable
migration is recorded
new evaluation is a new transition
new State is derived only through the v2 rules
```

## Case C — Migration cannot be completed

Some historical Evidence lacks information required by Protocol v2.

Result:

```text
migration_status: incomplete
historical Evidence: preserved
v1 State: recoverable
v2 projection: partial or unavailable
```

The missing information is not fabricated.

## Result

Protocol migration is not a file conversion. It is a controlled semantic transition with explicit lineage.

## Implication

Shirakami OS can evolve Protocols without requiring the historical Landscape to be rewritten. Old Protocols remain part of the historical interpretation chain, while current State may be projected under a newer Protocol after an explicit migration transition.

## Non-claim

This does not define automatic migration algorithms. It defines the invariant and authority boundary that any migration implementation must satisfy.
