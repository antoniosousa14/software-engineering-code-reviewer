# Software Engineering Code Reviewer

Software Engineering Code Reviewer is an AI coding agent instruction pack for senior-level code review, refactoring, architecture guidance, and maintainability.

It is primarily designed for coding agents such as Codex, Claude Code, Cursor, Windsurf, Cline, Aider, Google Antigravity, and similar tools.

It also includes an optional ChatGPT Skill package at `dist/skill.zip`.

## Why this exists

AI-generated code can work and still carry weak architecture, unclear naming, poor boundaries, low testability, and hidden future cost.

This instruction pack pushes coding agents beyond code that merely runs. It helps them reason about maintainability, correctness, cohesion, coupling, encapsulation, error handling, architecture, and tests without defaulting to unnecessary patterns.

## Quick start

### Use with an AI coding agent

1. Open this repository in the coding agent or editor.
2. Ask the agent to read `AGENTS.md`.
3. For Claude Code, use `CLAUDE.md`.
4. For Codex, use `CODEX.md`.
5. For Cursor, Windsurf, Cline, or Aider, use `CURSOR.md`.
6. Ask the agent to read focused files in `software-engineering-code-reviewer/references/` when needed.
7. Provide the code, requirements, constraints, and desired scope.

Coding agents use repository files directly. They do not use `dist/skill.zip`.

### Optional: install in ChatGPT

1. Download `dist/skill.zip`.
2. Upload or import it in ChatGPT's current Skills area.
3. Do not upload the full GitHub repository zip.

`dist/skill.zip` is only for ChatGPT Skill installation.

## Mental model

| Situation | Use | Do not use |
| --- | --- | --- |
| Codex / Cursor / Windsurf / Cline / Aider / Antigravity | `AGENTS.md`, relevant agent file, and focused reference files | `dist/skill.zip` |
| Claude Code | `CLAUDE.md`, which imports `AGENTS.md` | `dist/skill.zip` |
| ChatGPT Skill installation | `dist/skill.zip` | full GitHub repository zip |
| Editing guidance | source files in the repository | files inside the zip |
| Updating ChatGPT package | rebuild `dist/skill.zip` from `software-engineering-code-reviewer/` | package the whole repository |

## Repository layout

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
|-- software-engineering-code-reviewer/
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

## Guidance contents

- `AGENTS.md`: main entry point for coding agents.
- `CLAUDE.md`: Claude Code entry point.
- `CODEX.md`: Codex-specific notes.
- `CURSOR.md`: Cursor, Windsurf, Cline, and Aider notes.
- `ANTIGRAVITY.md`: Google Antigravity notes.
- `software-engineering-code-reviewer/SKILL.md`: skill entrypoint and compact behavior summary.
- `software-engineering-code-reviewer/references/*.md`: detailed engineering guidance.
- `software-engineering-code-reviewer/agents/openai.yaml`: ChatGPT-only metadata.
- `dist/skill.zip`: optional ChatGPT Skill package.

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
- Useful polymorphism
- Dependency inversion when useful
- Idiomatic naming and style
- Validation
- Error handling
- Security basics
- Performance awareness
- Testability
- Maintainability
- Useful documentation
- Avoiding overengineering

The guidance uses FURPS+, SOLID pragmatically, GRASP pragmatically, clean architecture when useful, and the idioms of the language under review.

## Usage examples

```text
Read AGENTS.md and use this repository's guidance to review my code like a senior software engineer.
```

```text
Refactor this from prototype code into maintainable production code without overengineering it.
```

```text
Review this using FURPS+ and identify coupling, cohesion, naming, encapsulation, and testability issues.
```

```text
Suggest tests for the important behavior and explain the trade-offs in your refactor.
```

## Maintaining the package

Only rebuild `dist/skill.zip` when files under `software-engineering-code-reviewer/` change.

```bash
mkdir -p dist
rm -f dist/skill.zip

python - <<'PY'
from pathlib import Path
from zipfile import ZipFile, ZIP_DEFLATED

root = Path("software-engineering-code-reviewer")
out = Path("dist/skill.zip")
out.parent.mkdir(exist_ok=True)

with ZipFile(out, "w", ZIP_DEFLATED) as zip_file:
    for path in root.rglob("*"):
        if path.is_file():
            zip_file.write(path, path.relative_to(root).as_posix())
PY

python -m zipfile -l dist/skill.zip
```

The zip root must contain:

- `SKILL.md`
- `agents/openai.yaml`
- `references/review-behavior.md`
- `references/engineering-rubric.md`
- `references/furps-quality-lens.md`
- `references/architecture-principles.md`
- `references/refactoring-playbook.md`
- `references/naming-and-style.md`
- `references/response-templates.md`

The zip must not contain outer repository files, the outer repository folder, a top-level `software-engineering-code-reviewer/` folder, or Windows backslash separators.

## License

MIT. See `LICENSE`.
