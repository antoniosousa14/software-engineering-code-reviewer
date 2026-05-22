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
├── README.md
├── CHANGELOG.md
├── LICENSE
├── .gitattributes
├── .gitignore
├── AGENTS.md
├── CLAUDE.md
├── CODEX.md
├── ANTIGRAVITY.md
├── CURSOR.md
├── skill/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       ├── review-behavior.md
│       ├── engineering-rubric.md
│       ├── furps-quality-lens.md
│       ├── architecture-principles.md
│       ├── refactoring-playbook.md
│       ├── naming-and-style.md
│       └── response-templates.md
└── dist/
    └── skill.zip
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

1. Clone or open this repository.
2. Read `AGENTS.md` and `CODEX.md`.
3. Edit files under `skill/`.
4. Rebuild `dist/skill.zip` from the contents of `skill/`.
5. Inspect the zip contents and confirm `SKILL.md` is at the zip root.
6. Commit the changes with a clear message.

## Use with Claude Code

1. Clone or open this repository.
2. Read `AGENTS.md` and `CLAUDE.md`.
3. Edit files under `skill/`.
4. Rebuild `dist/skill.zip` from the contents of `skill/`.
5. Inspect the zip contents and confirm no outer repository files are included.
6. Commit the changes with a clear message.

## Use with Google Antigravity

1. Clone or open this repository.
2. Read `AGENTS.md` and `ANTIGRAVITY.md`.
3. Edit files under `skill/`.
4. Rebuild `dist/skill.zip` from the contents of `skill/`.
5. Inspect the zip contents.
6. Commit the changes.

## Use with Cursor / Windsurf / Cline / Aider

1. Open this repository in the editor or agent environment.
2. Add `AGENTS.md` and the relevant agent instruction file to context.
3. Ask the agent to modify files under `skill/`.
4. Rebuild `dist/skill.zip` from `skill/`.
5. Inspect the zip contents.
6. Commit the changes.

Platform-specific UI can evolve. This repository provides the skill package and maintenance instructions; each platform's current import or context workflow should be followed where applicable.

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

## Updating the skill

Update files under `skill/`. Keep `SKILL.md` concise and move detailed behavior into `skill/references/`.

After every meaningful change:

1. Validate `skill/SKILL.md` frontmatter contains only `name` and `description`.
2. Rebuild `dist/skill.zip`.
3. Inspect the zip contents.
4. Confirm outer repository files are not included.
5. Commit the source and generated package together.

## Development workflow

1. Read `AGENTS.md`.
2. Choose the agent-specific instruction file if relevant.
3. Edit the smallest useful set of files.
4. Keep the skill language-agnostic.
5. Avoid numeric scoring systems.
6. Preserve "senior reviewer by default, mentor only when asked."
7. Package the skill.
8. Verify the package.
9. Commit the change.

## Packaging instructions

PowerShell:

```powershell
New-Item -ItemType Directory -Force dist
Compress-Archive -Path skill\* -DestinationPath dist\skill.zip -Force
```

Unix-like shells:

```sh
mkdir -p dist
cd skill
rm -f ../dist/skill.zip
zip -r ../dist/skill.zip .
```

The zip root must contain `SKILL.md`, `agents/`, and `references/`. It must not contain the outer `skill/` folder itself.

## Verifying the zip

Use:

```sh
tar -tf dist/skill.zip
```

Expected entries:

```text
SKILL.md
agents/openai.yaml
references/review-behavior.md
references/engineering-rubric.md
references/furps-quality-lens.md
references/architecture-principles.md
references/refactoring-playbook.md
references/naming-and-style.md
references/response-templates.md
```

Do not publish the zip if it contains `README.md`, `CHANGELOG.md`, `LICENSE`, `AGENTS.md`, `CLAUDE.md`, `CODEX.md`, `ANTIGRAVITY.md`, `CURSOR.md`, or an outer `software-engineering-code-reviewer/` directory.

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

### Should `dist/skill.zip` be committed?

Yes. This repository keeps the generated ChatGPT Skill package in `dist/skill.zip` so it is ready to publish or upload.

## License

MIT. See `LICENSE`.
