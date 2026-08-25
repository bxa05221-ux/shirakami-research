# Boundary Independence Test 001

Status: Initial executable probe
Version: 0.1

## Question

Can semantically different Protocols cross the current Shirakami Runtime boundary without requiring a Runtime change?

This experiment deliberately makes a narrower claim than "Shirakami OS is a new computational model." It tests the current implementation boundary.

## Current hypothesis

> Semantic differences can remain local to the Protocol while the Runtime consumes only the common execution boundary and a `Transition` result.

## Protocol domains

- cognitive observation
- conversation
- care observation
- game state
- repository observation
- organization workflow

## Probe design

All six Protocols are executed through the same `Runtime` instance. Each returns the same transition kind:

`boundary.independence.observed`

The semantic domain is kept inside the Protocol closure rather than interpreted by Runtime.

A second probe increases the amount of contextual data supplied to the same Runtime boundary.

## What the test can establish

If the probes pass, they provide executable evidence that the current Runtime boundary can accept different semantic domains without a domain-specific Runtime branch.

## What the test cannot establish

It does **not** prove:

- that the architecture is globally semantic-independent;
- that an Interpreter can never become necessary;
- that the design is a new computational model;
- that the design is novel relative to all prior systems.

Those require broader implementation and comparative research.

## Evidence

Executable test added to `shirakami-OS`:

`tests/test_boundary_independence_001.py`

The current Runtime implementation accepts a callable Protocol, constructs an `ExecutionContext`, executes the Protocol, validates the returned `Transition`, and produces an `ExecutionResult`. The probe therefore targets the actual implementation boundary rather than a hypothetical future Runtime.

## Next step

Run the repository test suite and record the observed result. If the probe passes, add a negative/control case in which a deliberately domain-dependent Runtime implementation is used, demonstrating that the test is capable of detecting a boundary violation rather than merely confirming success.
