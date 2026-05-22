# Software Engineering Code Reviewer

## What this is

Software Engineering Code Reviewer is a ChatGPT Skill that guides an AI coding agent to review, refactor, write, and improve code with senior software engineering standards.

It is not a code execution tool. It is an instruction and reasoning skill for agentic coding tools that need to produce clear, maintainable, testable, idiomatic, architecture-aware software across programming languages.

## What problem it solves

AI coding agents often optimize for code that runs, compiles, or satisfies a narrow prompt. That is not enough for production software.

This skill pushes the agent to evaluate code through maintainability, correctness, testability, encapsulation, separation of concerns, error handling, architecture, and long-term change cost. It helps move prototype, beginner, messy, or "vibe code" toward professional engineering quality without forcing unnecessary patterns.

## Philosophy

The agent should not say code is good just because it works. It should act like a direct senior reviewer: diagnose the important issues, preserve existing behavior before refactoring, propose concrete improvements, and explain trade-offs when they matter.

The skill is intentionally practical. It avoids numeric scores, academic theory, and pattern-heavy rewrites. A simple well-named function is often better than an elaborate abstraction.

## What the skill enforces

- Requirements awareness and behavior preservation
- Clear design and coherent architecture
- Separation of concerns and single responsibility
- High cohesion and low coupling
- Encapsulation and protection of invariants
- Appropriate abstraction without overengineering
- Polymorphism when it removes real behavioral branching
- Dependency inversion when it reduces coupling to volatile details
- Idiomatic naming and style for the target language
- Validation, error handling, and security basics
- Performance awareness without premature optimization
- Testability, maintainability, and useful documentation

## Quality lenses used

The skill uses practical versions of:

- FURPS+: Functionality, Usability, Reliability, Performance, Supportability, plus constraints
- SOLID, applied pragmatically rather than dogmatically
- GRASP: Information Expert, Controller, Creator, Pure Fabrication, High Cohesion, Low Coupling, Polymorphism, and Protected Variations
- Clean Architecture and layered architecture when the problem benefits from those boundaries
- Domain logic separated from UI, database, network, filesystem, framework, and infrastructure details when that separation improves clarity and testability

## Repository structure

```text
software-engineering-code-reviewer/
|-- README.md
|-- CHANGELOG.md
|-- LICENSE
|-- .gitattributes
|-- .gitignore
|-- AGENTS.md
|-- CLAUDE.md
|-- CODEX.md
|-- ANTIGRAVITY.md
|-- CURSOR.md
|-- skill/
|   |-- SKILL.md
|   |-- agents/
|   |   `-- openai.yaml
|   `-- references/
|       |-- review-behavior.md
|       |-- engineering-rubric.md
|       |-- furps-quality-lens.md
|       |-- architecture-principles.md
|       |-- refactoring-playbook.md
|       |-- naming-and-style.md
|       `-- response-templates.md
`-- dist/
    `-- skill.zip
```

## What is inside the skill

The installable skill package contains only the contents of `skill/`:

- `SKILL.md`: concise trigger metadata and core behavior instructions
- `agents/openai.yaml`: ChatGPT UI metadata
- `references/review-behavior.md`: senior reviewer behavior rules
- `references/engineering-rubric.md`: checklist-style engineering review rubric
- `references/furps-quality-lens.md`: practical FURPS+ review lens
- `references/architecture-principles.md`: architecture and design guidance
- `references/refactoring-playbook.md`: problem-to-action refactoring guide
- `references/naming-and-style.md`: language-aware naming and style guidance
- `references/response-templates.md`: adaptable response templates

Outer repository files are documentation and agent instructions. They are not included inside `dist/skill.zip`.

## Installation tutorials

## Install in ChatGPT

Use `dist/skill.zip` as the installable skill package.

Open ChatGPT's current Skills upload or import flow and upload `dist/skill.zip`. Exact UI wording may change, so follow the current ChatGPT Skills interface or official import instructions available in the product.

## Use with Codex

Use this skill as review guidance when asking Codex to work on your code.

1. Add the skill instructions to Codex using the current custom-instructions, context, or skill flow supported by your environment.
2. Provide the codebase, file, diff, or code snippet you want reviewed.
3. Ask Codex for the review style you want, such as a quick review, full refactor, architecture review, or test plan.
4. Tell Codex whether behavior must be preserved.
5. Ask for explanations only when you want mentor-style teaching.

## Use with Claude Code

Use this skill as senior-reviewer guidance when asking Claude Code to inspect or improve code.

1. Add the skill instructions to Claude Code using the current project-instructions or context mechanism.
2. Open the project or provide the relevant files.
3. Ask for concrete review findings, a behavior-preserving refactor, or test recommendations.
4. Include important requirements, constraints, and expected behavior.

## Use with Google Antigravity

Use this skill as code-quality guidance when asking Antigravity to review or improve a project.

1. Attach or load the skill instructions using Antigravity's current instruction or context flow.
2. Provide the relevant code and describe what the software is supposed to do.
3. Ask for a senior-level review focused on correctness, architecture, maintainability, and tests.

## Use with Cursor / Windsurf / Cline / Aider

Use this skill as instruction context for editor-based coding agents.

1. Open the codebase you want reviewed in your editor.
2. Add the skill instructions to the agent's context or custom instructions.
3. Ask the agent to review, refactor, or improve your code using senior software engineering standards.
4. Provide constraints such as language, framework, expected behavior, and whether the change should be minimal.

Platform-specific UI can evolve. Follow the platform's current official flow for adding custom instructions, attaching context, or importing skills.

## Usage tutorials

After installing or loading the skill, ask the AI agent to review, refactor, write, or improve code with senior engineering standards.

Good requests include the code, language, relevant requirements, known constraints, and whether you want a quick review, full refactor, architecture review, or teaching explanation.

For code review, provide:

- The code or files to review
- Expected behavior
- Known bugs or constraints
- Runtime, framework, or deployment context
- Whether behavior must remain unchanged

For refactoring, provide:

- The current code
- The behavior that must be preserved
- Any tests that already exist
- The preferred scope of change
- Whether you want patch-sized changes or a fuller redesign

## Getting the latest version

Download the latest `dist/skill.zip` from this repository and import it again using the current ChatGPT Skills flow. If your agent platform uses custom instructions instead of skill packages, refresh the instruction context from the latest skill files.

## Examples of prompts

- "Review this code like a senior engineer and propose a refactor."
- "Refactor this from prototype code into maintainable production code."
- "Improve the architecture without overengineering it."
- "Explain why your refactor is better."
- "Review this using FURPS+."
- "Identify coupling, cohesion, naming, encapsulation, and testability issues."
- "Rewrite this code in a more idiomatic style for this language."
- "Suggest tests for the important behavior."

## Examples of expected behavior

For a quick review, the agent should identify the most important risks first, explain their impact, and propose concrete fixes.

For a refactor, the agent should preserve behavior, make small coherent changes, improve naming and boundaries, and recommend tests for important behavior.

For architecture feedback, the agent should separate real design problems from stylistic preferences and explain trade-offs.

For teaching mode, the agent should slow down and explain why the proposed design is better, but only when the user asks for that style.

## FAQ

### Is this skill tied to one programming language?

No. It is language-agnostic and instructs the agent to follow the idioms of the language being reviewed.

### Does it enforce SOLID everywhere?

No. SOLID is used as a lens, not a rulebook. The skill rejects pattern abuse and unnecessary abstractions.

### Does it generate numeric code quality scores?

No. It uses checklist-style review, concrete findings, and actionable improvements instead of numeric ratings.

### Does it replace tests or static analysis?

No. It guides reasoning and review behavior. Tests, linters, type checkers, security scanners, and profilers remain valuable.

## License

MIT. See `LICENSE`.
