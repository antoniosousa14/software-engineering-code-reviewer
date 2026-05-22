# Engineering Rubric

Use this as a checklist, not a scoring system. Select the categories relevant to the task and focus on the highest-impact issues.

## Requirement fit

- Does the code satisfy the stated behavior?
- Are important requirements missing, ambiguous, or contradicted by the implementation?
- Are assumptions explicit?

## Behavior correctness

- Are normal, edge, and failure paths handled?
- Are state transitions valid?
- Are boundary conditions clear?
- Could concurrency, ordering, timing, or partial failure break behavior?

## Architecture

- Are responsibilities placed in coherent modules?
- Does the design match the size and volatility of the problem?
- Are framework, infrastructure, and domain concerns separated where useful?
- Is the design understandable without excessive indirection?

## Separation of concerns

- Is UI, database, network, filesystem, framework, and business logic mixed together?
- Can core logic be tested without heavy infrastructure?
- Are orchestration and domain rules distinct where that distinction helps?

## Cohesion

- Do functions, classes, and modules have one clear reason to change?
- Are related rules grouped together?
- Are unrelated operations forced into the same unit?

## Coupling

- Does code know too much about concrete dependencies?
- Are volatile details isolated behind stable boundaries where useful?
- Can important behavior change without touching many unrelated files?

## Encapsulation

- Are invariants protected by the owning type or module?
- Is mutable state exposed unnecessarily?
- Can callers put objects into invalid states?

## State and invariants

- Are valid states explicit?
- Are invalid states prevented rather than cleaned up later?
- Are lifecycle transitions clear?

## Abstraction quality

- Does each abstraction remove real complexity?
- Is polymorphism used for real behavioral variation?
- Are interfaces introduced only where they reduce coupling or improve tests?
- Is the code avoiding speculative generality?

## Naming

- Do names express domain intent?
- Are vague names such as `data`, `info`, `temp`, `thing`, `doStuff`, `handle`, `manager`, `helper`, and `utils` avoided unless they are precise in context?
- Do boolean names read as predicates?

## Idiomatic language style

- Does the code look native to the target language?
- Are language conventions for naming, errors, modules, types, and resource handling followed?
- Does the code avoid patterns imported awkwardly from another language?

## Duplication

- Is duplication accidental or intentional?
- Does repeated logic hide a missing domain concept?
- Would extraction improve clarity without creating premature abstraction?

## Error handling

- Are errors handled at the right level?
- Are failures explicit, actionable, and observable?
- Are exceptions, result types, optional values, or error returns used according to language idiom?

## Validation

- Are inputs validated at trust boundaries?
- Are domain invariants validated near the domain model or use case?
- Are validation failures clear to callers or users?

## Security basics

- Are untrusted inputs treated as untrusted?
- Are authentication, authorization, injection, secrets, and sensitive data exposure considered?
- Are dependencies and external calls used safely?

## Performance

- Are obvious performance traps avoided?
- Are data structures and algorithms reasonable for expected scale?
- Is optimization driven by constraints or evidence rather than guesswork?

## Testability

- Can meaningful logic be tested without UI, network, filesystem, database, or time dependencies?
- Are normal, edge, and failure paths covered or clearly recommended?
- Are tests coupled to behavior rather than implementation details?

## Maintainability

- Can a future engineer understand and change the code confidently?
- Are responsibilities, names, and boundaries stable under likely changes?
- Are complex decisions documented where useful?

## Documentation

- Do comments explain why rather than repeat what the code says?
- Are public APIs, non-obvious behavior, and operational constraints documented?
- Is documentation consistent with the code?

## Dependency management

- Are dependencies justified?
- Are external libraries isolated where replacement or testing may matter?
- Are version, licensing, security, and maintenance risks considered when relevant?

## Observability when applicable

- Are important failures logged with useful context?
- Are metrics, traces, or audit records considered for production workflows?
- Are logs safe and free of secrets or sensitive data?
