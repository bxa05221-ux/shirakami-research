# MP0001 Test 01 — Multi-form representation

status: experiment
contract: MP0001
source_evidence: E0002-matome-incompleteness-useful.md
source_delta: D0001

## Representation A — YAML

```yaml
observation: "Matome was incomplete and useful"
status: observed
unresolved:
  - why incompleteness was useful
  - whether YAML caused the usefulness
```

## Representation B — JSON

```json
{
  "observation": "Matome was incomplete and useful",
  "status": "observed",
  "unresolved": [
    "why incompleteness was useful",
    "whether YAML caused the usefulness"
  ]
}
```

## Representation C — Markdown

Observation: Matome was incomplete and useful.

Status: observed.

Unresolved: why incompleteness was useful; whether YAML caused the usefulness.

## Preserved relations

- source evidence identity
- source delta identity
- observed statement
- unresolved questions
- non-claim boundary

## Representation-specific changes

- syntax
- structural encoding
- degree of explicit metadata

## Result

The same observed relation can be represented in multiple forms without changing the source Evidence identity. This experiment does not establish that all future representations preserve the same information, only that these three representations can preserve the tested relations.
