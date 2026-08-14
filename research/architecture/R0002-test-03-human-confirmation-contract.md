# R0002 Test 03 — Human confirmation contract

status: experimental_contract
parent_contract: R0002

## Question

When does a human confirmation become a new Evidence candidate rather than merely conversational acknowledgement?

## Candidate conditions

A confirmation should be treated as an Evidence candidate only when:

1. the human explicitly confirms or restates the proposition;
2. the confirmed content is distinguishable from the preceding AI formulation;
3. the source interaction is recoverable;
4. the proposition has a defined observation boundary;
5. uncertainty is preserved where the human confirmation remains tentative.

## Example

AI: "つまり、不完全であること自体に価値があった、ということですね。"

Human A: "うん。"

Human A is an acknowledgement, but the exact proposition being confirmed may remain ambiguous.

Human B: "そう。不完全だからこそ役に立ったと思う。"

Human B contains an explicit human-originated proposition and can become an Evidence candidate, subject to the normal verification state.

## Result

Human presence alone is insufficient. Even a human response may be ambiguous.

The Runtime should therefore distinguish:

- acknowledgement;
- explicit confirmation;
- human restatement;
- human revision;
- human rejection.

## Implication

Evidence creation is a state transition, not a speaker-label assignment.

`actor_kind: human` identifies provenance, but `verification_state` determines whether the content has crossed the Evidence boundary.

## Non-claim

This does not define a universal linguistic classifier. It defines the minimum conceptual distinction required for the current experiment.
