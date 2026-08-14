# R0004 — Coordination scope: single-human and multi-human Landscapes

status: experimental_contract
parent_contracts:
  - R0002
  - R0003

## Question

Does the conflict and verification model change when a Landscape belongs to one human versus multiple humans?

## Single-human Landscape

A single human may own or control the Landscape while AI systems act as assistants or observers.

Coordination remains necessary when:
- the human has not resolved a conflict;
- multiple verified propositions coexist;
- external evidence conflicts with the user's current state;
- permissions or provenance are ambiguous.

The Runtime must not treat "single user" as permission to resolve every semantic conflict automatically.

## Multi-human Landscape

When multiple human actors contribute to the same Landscape, each contribution retains its own actor identity, content origin, Evidence lineage, and verification state.

Agreement between humans is itself an observable transition.
Disagreement is also an observable state and must not be collapsed into a single winner without an authorized coordination rule.

## Coordination model

```text
Actor Evidence
      ↓
Individual Verification
      ↓
Shared Landscape Candidate
      ↓
Agreement / Conflict
      ↓
Coordination Protocol
      ↓
New Verified Transition
```

## Result

The underlying Evidence model does not need separate foundations for single-human and multi-human Landscapes.

What changes is the coordination topology and authorization policy.

## Implication

`actor_kind` and `actor_id` remain provenance fields at every scale.
Coordination should be represented as a protocol layer above Evidence verification rather than embedded inside the Runtime's semantic judgment.

## Non-claim

This does not define voting, consensus, organizational governance, or access-control mechanisms. It establishes only that multi-actor coordination is a distinct layer and that single-actor Landscapes still require explicit conflict handling.
