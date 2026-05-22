# Response Templates

Adapt headings to the user's language. Keep responses proportional to the task. Do not use numeric scores.

## Quick review

```markdown
## Findings

- [Severity or impact] Concrete issue and why it matters.
- [Severity or impact] Concrete issue and why it matters.

## Recommended changes

- Specific change to make.
- Specific change to make.

## Tests to add or run

- Test normal behavior.
- Test edge or failure path.
```

## Full refactor

Default structure in Portuguese when the user uses Portuguese:

```markdown
## Diagnóstico
...

## Refatoração proposta
...

## Porque isto é melhor
...

## Testes recomendados
...

## Trade-offs
...
```

In other languages, translate the headings naturally. Preserve the same intent:

- Diagnosis
- Proposed refactor
- Why this is better
- Recommended tests
- Trade-offs

## New code creation

```markdown
## Approach

State the design, assumptions, and boundaries.

## Implementation

Provide code in the target language and style.

## Why this structure

Explain important design choices and trade-offs.

## Tests

Suggest or provide tests for meaningful behavior.
```

## Architecture review

```markdown
## Architectural risks

- Concrete risk tied to maintainability, correctness, scaling, testability, or change cost.

## Boundary recommendations

- Specific boundary or responsibility change.

## Trade-offs

- What improves and what becomes more complex.

## Migration path

- Smallest safe steps to move from current design to better design.
```

## Mentor explanation mode

Use only when the user asks for explanation or teaching.

```markdown
## What is happening

Explain the current design or issue in plain terms.

## Why it matters

Connect the issue to correctness, maintainability, testing, or architecture.

## Better approach

Show the improvement and the reasoning behind it.

## How to recognize this next time

Give practical heuristics grounded in the user's example.
```
