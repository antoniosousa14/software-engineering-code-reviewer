# Software Engineering Code Reviewer

## What this is

Software Engineering Code Reviewer is an AI agent guidance repository with an installable ChatGPT Skill package.

This repository provides AI-agent guidance for senior-level code review, refactoring, architecture improvement, and maintainability work across programming languages. It is meant for Codex, Claude Code, Google Antigravity, Cursor, Windsurf, Cline, Aider, ChatGPT, and similar AI coding agents.

The ChatGPT-specific source and package are contained inside the broader repository. Use `skill/` as the source of the skill. Use `dist/skill.zip` as the installable ChatGPT Skill package.

## Quick start

### I just want to use the ChatGPT Skill

1. Download `dist/skill.zip`.
2. Open ChatGPT.
3. Go to the current Skills upload or import area.
4. Upload `dist/skill.zip`.
5. Start a new chat and ask for code review, refactoring, or architecture guidance.

Do not upload the full GitHub repository zip. Upload `dist/skill.zip`.

Example prompt:

```text
Review this code like a senior software engineer and improve it without overengineering.
```

### I want to use this with another AI coding agent

1. Open or clone this repository.
2. Give the agent `AGENTS.md` and the matching agent note such as `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, or `CURSOR.md`.
3. Ask the agent to review or improve the code you care about using this repository guidance.

Example prompt:

```text
Use this repository guidance to review the selected code for architecture, maintainability, and testability issues.
```

### I want to maintain the ChatGPT Skill package

1. Edit the source files under `skill/`.
2. Rebuild `dist/skill.zip`.
3. Verify the zip contents.
4. Commit the source changes and the updated package together.

## What problem it solves

AI-generated code often works while still falling short of professional engineering standards. It can hide weak architecture, poor maintainability, low testability, unclear naming, leaky responsibilities, fragile error handling, or shortcuts that raise the cost of the next change.

This guidance pushes an agent past "it runs" toward code a team can review, test, evolve, and defend technically.

## Philosophy

Do not optimize only for code that works. Optimize for code that is clear, maintainable, testable, extensible, robust, idiomatic, and architecture-aware.

Stay practical. Avoid overengineering, pattern abuse, and rewrites that add ceremony without reducing real complexity. A simple well-named function can be better than an unnecessary design pattern.

Professional code is code that a team can maintain, test, evolve, and defend technically.

## What the guidance enforces

- Requirements awareness
- Coherent design
- Clean architecture where useful
- Separation of concerns
- Single responsibility
- High cohesion
- Low coupling
- Encapsulation
- Protection of invariants
- Appropriate abstraction
- Polymorphism when useful
- Dependency inversion when useful
- Language-idiomatic naming and style
- Validation
- Error handling
- Security basics
- Performance awareness without premature optimization
- Testability
- Maintainability
- Useful documentation
- Avoiding overengineering

## Quality lenses used

- FURPS+
- SOLID, not dogmatically
- GRASP
- Clean Architecture or layered architecture when appropriate
- Idiomatic language conventions
- Maintainability and testability

## Repository structure

```text
software-engineering-code-reviewer/
|-- README.md
|-- CHANGELOG.md
|-- LICENSE
|-- .gitignore
|-- AGENTS.md
|-- CODEX.md
|-- CLAUDE.md
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

- `README.md` explains the project, installation paths, usage, and maintenance workflow.
- `AGENTS.md` defines repository-wide instructions for coding agents.
- `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, and `CURSOR.md` provide agent-specific repository guidance.
- `skill/` is the source for the installable ChatGPT Skill package.
- `dist/skill.zip` is the generated ChatGPT Skill package built from `skill/`.
- `CHANGELOG.md`, `LICENSE`, and `.gitignore` cover release history, licensing, and repository hygiene.

## What is inside the skill

- `skill/SKILL.md` contains the main ChatGPT Skill instructions and concise behavior rules.
- `skill/agents/openai.yaml` contains ChatGPT UI metadata.
- `skill/references/*.md` contains modular review, architecture, refactoring, naming, and response guidance loaded when relevant.
- `dist/skill.zip` is generated from the contents of `skill/`.

Outer repository files document the project and guide maintenance. They must stay outside the package archive.

## Installation and use

### Install in ChatGPT

Use `dist/skill.zip` to install the ChatGPT Skill. Do not upload the full GitHub repository zip.

Follow the current ChatGPT Skills upload or import UI. Exact UI labels may change, so this repository intentionally provides the zip rather than hardcoding UI-specific steps.

### Use with other AI coding agents

Use the repository instructions with Codex, Claude Code, Google Antigravity, Cursor, Windsurf, Cline, Aider, or similar AI coding agents.

1. Open or clone the repository.
2. Add `AGENTS.md` to the agent context.
3. Add the matching agent note when one exists: `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, or `CURSOR.md`.
4. Provide the code, requirements, constraints, and desired scope for the review or refactor.

You do not need to rebuild `dist/skill.zip` just to use the repository guidance with another agent.

### Agent notes

- Codex: read `AGENTS.md` and `CODEX.md`.
- Claude Code: read `AGENTS.md` and `CLAUDE.md`.
- Google Antigravity: read `AGENTS.md` and `ANTIGRAVITY.md`.
- Cursor, Windsurf, Cline, and Aider: read `AGENTS.md` and `CURSOR.md`.

## Usage

After installing the ChatGPT package or loading the repository guidance into another agent, provide the relevant code, requirements, constraints, and desired scope. State when behavior must be preserved before a refactor.

Example prompts:

- "Review this code like a senior engineer and propose a refactor."
- "Refactor this from prototype code into maintainable production code."
- "Improve the architecture without overengineering it."
- "Review this using FURPS+."
- "Identify coupling, cohesion, naming, encapsulation, and testability issues."
- "Rewrite this code in a more idiomatic style for this language."
- "Suggest tests for the important behavior."
- "Explain why your refactor is better."

## Examples of expected behavior

- Diagnose the code and its constraints before recommending a rewrite.
- Propose concrete refactors that improve naming, boundaries, responsibilities, or tests.
- Explain why important changes are better when they affect design, behavior, or maintenance cost.
- Recommend tests for important behavior, regressions, and risky refactors.
- Mention trade-offs when a design choice changes complexity, coupling, performance, or flexibility.
- Avoid numeric code-quality scores.

## Updating the skill

This section is for maintainers. Normal users can install `dist/skill.zip` without rebuilding it.

Make skill changes under `skill/`, then rebuild `dist/skill.zip`. Keep source files and the generated archive synchronized in the same change.

## Development workflow

1. Edit `skill/SKILL.md` only for core behavior.
2. Put detailed guidance in `skill/references/`.
3. Keep guidance language-agnostic.
4. Avoid numeric scoring.
5. Preserve the senior reviewer behavior.
6. Rebuild and verify the zip after every change.

## Packaging instructions

These commands are for maintainers rebuilding the ChatGPT Skill package after source changes.

Run the packaging recipe from the repository root:

```bash
mkdir -p dist
rm -f dist/skill.zip

python - <<'PY'
from pathlib import Path
from zipfile import ZipFile, ZIP_DEFLATED

root = Path("skill")
out = Path("dist/skill.zip")
out.parent.mkdir(exist_ok=True)

with ZipFile(out, "w", ZIP_DEFLATED) as zip_file:
    for path in root.rglob("*"):
        if path.is_file():
            zip_file.write(path, path.relative_to(root).as_posix())
PY
```

Windows PowerShell users can use the same Python zip method:

```powershell
python -c "from pathlib import Path; from zipfile import ZipFile, ZIP_DEFLATED; root=Path('skill'); out=Path('dist/skill.zip'); out.parent.mkdir(exist_ok=True); z=ZipFile(out,'w',ZIP_DEFLATED); [z.write(p, p.relative_to(root).as_posix()) for p in root.rglob('*') if p.is_file()]; z.close()"
```

### Verifying the zip

Inspect the package before committing:

```bash
python -m zipfile -l dist/skill.zip
```

The zip should contain exactly these skill files:

- `SKILL.md`
- `agents/openai.yaml`
- `references/review-behavior.md`
- `references/engineering-rubric.md`
- `references/furps-quality-lens.md`
- `references/architecture-principles.md`
- `references/refactoring-playbook.md`
- `references/naming-and-style.md`
- `references/response-templates.md`

The zip must not contain:

- `README.md`
- `CHANGELOG.md`
- `LICENSE`
- `AGENTS.md`
- `CODEX.md`
- `CLAUDE.md`
- `ANTIGRAVITY.md`
- `CURSOR.md`
- A top-level `skill/` folder
- The outer repository folder
- Windows backslash separators

## FAQ

### Is this only for ChatGPT?

No. The repository provides guidance for AI coding agents generally. `dist/skill.zip` is the installable ChatGPT package.

### Does this force overengineering?

No. The guidance rejects pattern abuse and prefers the smallest design that improves clarity, maintainability, testability, and change safety.

### Does it give code scores?

No. It uses concrete findings, refactoring guidance, and trade-offs instead of numeric scores.

### Does it work for any language?

Yes. The guidance is language-agnostic and expects agents to follow idioms of the language and ecosystem under review.

### What is the difference between `skill/` and `dist/skill.zip`?

`skill/` is the editable source for the ChatGPT Skill. `dist/skill.zip` is the generated installable package built from that source.

## License

MIT. See `LICENSE`.
