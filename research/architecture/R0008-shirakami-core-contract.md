# R0008 — Shirakami Core Contract

status: experimental_consolidation
parent_contracts:
  - R0003
  - R0004
  - R0005
  - R0006
  - R0007

## Purpose

Consolidate the experimentally established architecture boundaries before implementation-specific schema work.

## Core invariant

```text
Landscape continuity is preserved by:
  Evidence lineage
  + Protocol lineage
  + Semantic State
```

AI implementation, Runtime implementation, projection format, and backend may change without automatically destroying Landscape continuity.

## Authority model

```text
Permission
  = operation authorization

Provenance
  = origin of event/content

Eligibility
  = permission to enter a controlled transition

Verification
  = protocol-defined evidence status

Semantic Effect
  = authorized consequence for Landscape State

Projection
  = derived representation
```

These concepts must not collapse into one trust or authority flag.

## Transition model

```text
Observation
  ↓
Eligibility
  ↓
Verification
  ↓
Semantic Effect
  ↓
Landscape State
  ↓
Projection
```

`accepted`, `verified`, and `applied` are distinct states.

Rejected and unresolved outcomes remain observable and immutable; they do not automatically produce semantic effects.

## Conflict model

Projection divergence is handled at Runtime/Adapter level.

Semantic conflict is handled through Protocol/Coordination.

AI disagreement remains a hypothesis or counter-observation until it crosses the applicable Evidence and verification boundary.

## Migration model

Protocol migration is a semantic transition, not file conversion.

Runtime upgrades must not rewrite historical Evidence.

Protocol upgrades must preserve historical interpretation and establish new interpretation through explicit migration lineage.

Incomplete migration preserves historical state and records the missing basis rather than fabricating it.

## Runtime responsibility

Runtime:

- observes events;
- evaluates Protocol-declared eligibility;
- records observations and outcomes;
- executes permitted transitions;
- preserves Evidence and lineage;
- materializes projections;
- exposes Landscape State to Adapters.

Runtime does not invent domain-specific semantic truth.

## Protocol responsibility

Protocol declares:

- required eligibility conditions;
- verification rules;
- legal transitions;
- semantic effects;
- migration rules where applicable.

Protocol does not rewrite immutable historical Evidence.

## Current research boundary

This document is a consolidation of tested architectural conclusions, not a final implementation schema.

The next phase should translate this contract into concrete Event, Evidence, State, Transition, Permission, and Adapter interfaces and test them against real Runtime behavior.
