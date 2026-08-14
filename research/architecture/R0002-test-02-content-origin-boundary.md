# R0002 Test 02 — Content-origin boundary

status: tested
parent_contract: R0002

## Test cases

### Case A — Human statement

Human: "的目は不完全だったけど役に立った。"

Classification:
- actor_kind: human
- content_origin: human
- status: evidence_candidate

### Case B — AI paraphrase

AI: "つまり、的目は不完全であること自体に価値があった、ということですね。"

Classification:
- actor_kind: ai
- content_origin: ai_paraphrase
- status: hypothesis_or_candidate

The paraphrase may preserve the human statement, but the causal phrase "価値があった" must not be promoted to human Evidence unless the human confirms it.

### Case C — Human confirmation

Human: "そう。それが役に立った理由だと思う。"

Classification:
- actor_kind: human
- content_origin: human
- status: evidence_candidate

The human confirmation creates a new observable statement. It does not retroactively transform Case B into human Evidence.

## Result

Actor identity and content origin must be represented independently.

`actor_kind` answers who produced the event.
`content_origin` answers how the current content was produced.

## Boundary

AI may paraphrase human content, but paraphrase remains AI-originated until separately confirmed by the human.

Human confirmation creates new Evidence candidate content; it does not rewrite the provenance of earlier AI output.

## Implication

This boundary should exist below the Matome surface. A Matome may display a human-confirmed relation without exposing the complete provenance metadata, while Runtime preserves the distinction.

## Non-claim

This test does not define the complete ontology of content origins. It establishes only the minimum distinction needed to prevent AI paraphrase from silently becoming human Evidence.
