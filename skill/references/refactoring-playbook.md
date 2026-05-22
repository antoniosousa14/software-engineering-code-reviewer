# Refactoring Playbook

Preserve behavior first. Prefer small, reviewable refactors unless the user asks for a larger redesign.

## Problem to action

| Problem | Practical action |
| --- | --- |
| Giant function | Split by intention: validation, calculation, orchestration, formatting, side effects. |
| God class | Separate responsibilities into cohesive collaborators or modules. |
| Repeated `if`/`else` or `switch` by type | Consider polymorphism, strategy, dispatch maps, or rule objects when variation is real and recurring. |
| Public mutable state | Encapsulate state and expose behavior that protects invariants. |
| Duplicated logic | Extract a shared concept when duplication represents the same rule. Keep duplication if extraction would hide different concepts. |
| Business logic mixed with UI, database, API, network, or filesystem code | Move domain rules into a domain or use-case layer where useful. |
| Vague names | Rename by domain intent and responsibility. |
| Hard-coded dependencies | Inject dependencies or introduce an interface when it improves testability or isolates volatile infrastructure. |
| No tests | Add tests for normal, edge, and failure paths before or during refactoring. |
| Primitive obsession | Introduce a value object, type, enum, or small domain concept when it protects invariants or clarifies meaning. |
| Null-heavy code | Use explicit optional, result, guard, default, or error handling patterns that are idiomatic for the language. |
| Long parameter lists | Group related values into a parameter object or domain type when the group has meaning. |
| Boolean flag arguments | Split into intention-revealing functions or introduce a policy/strategy when behavior diverges. |
| Hidden side effects | Make side effects explicit in names, boundaries, or dependencies. |
| Temporal coupling | Make required ordering explicit through types, state transitions, or a use-case service. |
| Overbroad interface | Split by client need or replace with a narrower port. |
| Framework leakage | Move framework-specific code to adapters, controllers, or infrastructure modules. |
| Hard-to-test time, randomness, or external calls | Inject clock, random generator, client, or repository when useful. |
| Catch-all error handling | Catch specific failures, preserve context, and return or throw errors at the right abstraction level. |
| Premature abstraction | Inline or simplify until variation is real. |

## Refactoring sequence

1. Characterize current behavior.
2. Identify the smallest boundary that improves clarity or testability.
3. Add or recommend tests around important behavior.
4. Rename unclear concepts before moving logic when names block understanding.
5. Extract pure logic away from side effects when useful.
6. Encapsulate state and invariants.
7. Introduce abstractions only for real variation or volatile dependencies.
8. Re-run or recommend relevant tests.

## When not to refactor

Avoid refactoring when the change would increase complexity without reducing a real risk, when requirements are too unstable to justify new structure, or when the code is small enough that a clearer name or guard clause is sufficient.
