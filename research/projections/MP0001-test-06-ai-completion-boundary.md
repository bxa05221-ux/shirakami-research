# MP0001 Test 06 — AI completion boundary

status: experiment
contract: MP0001

## Test question

What happens when an AI adds context that was not present in the source Evidence/Delta while generating a Matome surface?

## Source

Observed statement:

> Matome was incomplete and useful.

## Artificially completed candidate

> The Matome was useful because its incompleteness preserved ambiguity and allowed the user to revise context over time.

## Comparison

Source-supported content:
- Matome was incomplete.
- The incompleteness was useful.

AI-added interpretation:
- incompleteness preserved ambiguity;
- incompleteness enabled later contextual revision;
- these were the reason for usefulness.

## Result

The completed candidate is more explanatory but contains claims not supported by the source Evidence/Delta pair.

It therefore cannot be promoted as an Evidence-derived Matome without additional Evidence or Counter-Evidence.

## Boundary

AI generation may:
- propose missing context as a Candidate;
- formulate questions;
- suggest possible relations.

AI generation must not:
- silently convert inference into observed fact;
- silently expand the Evidence scope;
- rewrite the source Evidence;
- present inferred context as if it came from the user.

## Conclusion

The compression engine and the completion engine must be separate operations.

Matome compression removes representation while preserving supported relations.
AI completion adds hypotheses and therefore moves in the opposite direction.
