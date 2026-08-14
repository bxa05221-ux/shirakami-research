# CE0002 — Counter-evidence: transition-only storage risk

status: tested
parent_experiment: D0002 Test 01
hypothesis_tested: Runtime may preserve only verified transition boundaries rather than every conversational turn.

## Counter-example

A conversational turn may contain a small qualification, hesitation, correction, or discarded alternative that is not immediately recognized as a Landscape transition.

If the Runtime stores only detected transition boundaries, that information may be lost before later dialogue reveals its significance.

## Result

Transition-only storage cannot be treated as lossless by default.

A boundary detector may miss latent information whose relevance becomes observable only later.

## Revised constraint

The Runtime may compress ordinary dialogue, but it must preserve enough recoverable source material to re-observe a disputed or newly significant transition.

## Consequence for Matome

Matome should not be the sole storage layer for conversational context.

A compact Matome surface may coexist with source dialogue, Evidence lineage, and re-observation capability.

## Non-claim

This does not require storing every turn forever. It establishes only that irreversible deletion before significance can be observed is unsafe.

## Next question

What minimum source retention is sufficient to permit later re-observation without turning the Runtime into a full transcript archive?
