# R0007 Test 01 — Semantic Protocol migration

status: experimental_contract
parent_contract: R0007

## Purpose

Demonstrate a Protocol v1 to v2 migration in which the semantic rule changes while historical Evidence remains recoverable.

## Protocol v1

```yaml
protocol_id: landscape_status
version: 1
eligibility:
  require:
    - human_confirmation
semantic_effect:
  confirmed: update_projection
```

## Protocol v2

```yaml
protocol_id: landscape_status
version: 2
eligibility:
  require:
    - human_confirmation
    - source_recoverability
    - conflict_status
semantic_effect:
  confirmed: update_projection
```

The semantic requirement has become stricter: v2 additionally requires recoverable source information and a resolved conflict state.

## Historical Event

```text
E1
actor_kind: human
content_origin: human
human_confirmation: confirmed
source_recoverability: unknown
conflict_status: unknown
protocol_version: 1
semantic_effect: update_projection
```

Under v1, E1 legitimately produced a projection update.

## Migration evaluation

Under v2, E1 cannot be silently reclassified as if it had originally been created under v2.

Instead:

```text
E1
 ↓
Historical v1 interpretation preserved
 ↓
Migration observation M1
 ↓
v2 eligibility check
 ↓
insufficient information
 ↓
migration_status: incomplete
```

## New Evidence

Suppose a later observation establishes:

```text
source_recoverability: confirmed
conflict_status: resolved
```

A new transition may then occur:

```text
E1 + new evidence
       ↓
M2
       ↓
v2 verification
       ↓
confirmed
       ↓
v2 semantic effect
```

## Result

Protocol migration preserves historical meaning while allowing new rules to produce a new, explicitly lineage-linked interpretation.

The original v1 transition is not rewritten.

## Key finding

A semantic Protocol migration requires **re-evaluation**, not textual conversion.

```text
Protocol v1 State
      ↓
Migration Observation
      ↓
Protocol v2 Evaluation
      ↓
New State / Incomplete Migration
```

## Non-claim

This test does not establish automatic migration. It demonstrates the required authority and lineage boundary for a semantic Protocol change.
