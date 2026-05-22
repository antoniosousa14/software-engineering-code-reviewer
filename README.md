# Software Engineering Code Reviewer

## What this is

Software Engineering Code Reviewer is an AI coding agent instruction pack for senior-level code review, refactoring, architecture guidance, and maintainability.

It is used by giving repository files as context to coding agents such as Codex, Claude Code, Cursor, Windsurf, Cline, Aider, Google Antigravity, and similar tools.

It also ships an optional ChatGPT Skill package at `dist/skill.zip`.

- Coding agents use Markdown files in the repository.
- Coding agents do not install or consume `dist/skill.zip`.
- `dist/skill.zip` is only for ChatGPT Skill installation.
- Rebuilding `dist/skill.zip` is only a maintainer task, and only needed when files under `skill/` change.
- `skill/agents/openai.yaml` exists only for ChatGPT Skill metadata.

## Mental model

| Situation | What to use | What not to use |
| --- | --- | --- |
| Reviewing or refactoring code with Codex, Claude Code, Cursor, Windsurf, Cline, Aider, Antigravity, or similar agents | `AGENTS.md`, the relevant agent file, `skill/SKILL.md`, and focused files in `skill/references/` | `dist/skill.zip` |
| Installing the optional ChatGPT Skill | `dist/skill.zip` | the full GitHub repository zip |
| Editing this repository's guidance | source files in the repository | editing files inside `dist/skill.zip` |
| Updating the optional ChatGPT Skill package | rebuild `dist/skill.zip` from `skill/` | packaging the whole repository |
| Changing only README or root documentation | commit the documentation changes | rebuilding `dist/skill.zip` |

- `AGENTS.md` is the main entry point for coding agents.
- Agent-specific files adapt repository usage for each tool.
- `skill/SKILL.md` and `skill/references/*.md` contain guidance that both coding agents and the optional ChatGPT Skill can use.
- `skill/agents/openai.yaml` is ChatGPT-only metadata.
- `dist/skill.zip` is only the optional ChatGPT Skill package.

## Quick start

### Primary: use with an AI coding agent

Use this for Codex, Claude Code, Cursor, Windsurf, Cline, Aider, Google Antigravity, or similar tools.

1. Open this repository in the coding agent or editor.
2. Ask the agent to read `AGENTS.md`.
3. Ask it to read the relevant agent file:
   - `CODEX.md` for Codex
   - `CLAUDE.md` for Claude Code
   - `ANTIGRAVITY.md` for Google Antigravity
   - `CURSOR.md` for Cursor, Windsurf, Cline, Aider, or similar editor-based agents
4. Ask it to read `skill/SKILL.md` and focused files in `skill/references/` when deeper guidance is needed.
5. Give it the code, requirements, constraints, and desired scope.

Do not give `dist/skill.zip` to coding agents. That zip is only for ChatGPT Skill installation.

Example prompts:

```text
Read AGENTS.md and use this repository's guidance to review my code like a senior software engineer.
```

```text
Read AGENTS.md and the relevant reference files, then refactor this code for maintainability without overengineering it.
```

### Optional: install the ChatGPT Skill

Use this only when you want the guidance installed in ChatGPT as a Skill.

1. Download `dist/skill.zip`.
2. Open ChatGPT.
3. Go to the current Skills upload or import area.
4. Upload `dist/skill.zip`.
5. Start a new chat and ask for code review, refactoring, or architecture guidance.

Do not upload the full GitHub repository zip. Upload `dist/skill.zip`.

```text
Review this code like a senior software engineer and improve it without overengineering.
```

`dist/skill.zip` is not needed when using this repository with coding agents.

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

- `README.md` explains the instruction pack, the optional ChatGPT package, usage, and maintenance workflow.
- `AGENTS.md` is the main repository-wide instruction entry point for coding agents.
- `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, and `CURSOR.md` provide agent-specific repository guidance.
- `skill/SKILL.md` and `skill/references/` provide reusable instruction context and are also packaged for the optional ChatGPT Skill.
- `skill/agents/openai.yaml` is ChatGPT Skill UI metadata. Coding agents do not need it.
- `dist/skill.zip` is the optional ChatGPT Skill package built from `skill/`.
- `CHANGELOG.md`, `LICENSE`, and `.gitignore` cover release history, licensing, and repository hygiene.

## Instruction files and optional ChatGPT package

- `AGENTS.md` defines the repository-wide operating model for coding agents.
- `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, and `CURSOR.md` adapt that context for specific coding-agent workflows.
- `skill/SKILL.md` contains concise core guidance that coding agents can read when useful and that ChatGPT uses inside the optional Skill package.
- `skill/references/*.md` contains modular review, architecture, refactoring, naming, and response guidance loaded when relevant.
- `skill/agents/openai.yaml` exists only for ChatGPT Skill UI metadata. It is irrelevant to Codex, Claude Code, Cursor, Windsurf, Cline, Aider, Google Antigravity, and other coding agents.
- `dist/skill.zip` is generated from `skill/` only for optional ChatGPT Skill installation or package maintenance.

Outer repository files document the project and guide maintenance. They must stay outside the package archive.

## Usage mode

### Use with coding agents

Use the repository files as instruction context with Codex, Claude Code, Google Antigravity, Cursor, Windsurf, Cline, Aider, or similar AI coding agents.

1. Start with `AGENTS.md`.
2. Add the matching agent note when one exists: `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, or `CURSOR.md`.
3. Load `skill/SKILL.md` or focused files from `skill/references/` when the task benefits from deeper guidance.
4. Provide the code, requirements, constraints, and desired scope for the review or refactor.

Coding agents do not install or consume `dist/skill.zip`.

### Agent notes

- Codex: read `AGENTS.md` and `CODEX.md`.
- Claude Code: read `AGENTS.md` and `CLAUDE.md`.
- Google Antigravity: read `AGENTS.md` and `ANTIGRAVITY.md`.
- Cursor, Windsurf, Cline, and Aider: read `AGENTS.md` and `CURSOR.md`.

### Optional: install in ChatGPT

Use `dist/skill.zip` to install the optional ChatGPT Skill. Do not upload the full GitHub repository zip.

Follow the current ChatGPT Skills upload or import UI. Exact UI labels may change, so this repository intentionally provides the zip rather than hardcoding UI-specific steps.

## Usage

After loading the repository guidance into a coding agent, or optionally installing the ChatGPT Skill package, provide the relevant code, requirements, constraints, and desired scope. State when behavior must be preserved before a refactor.

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

## Maintainer mode

This section is for editing this repository. Coding-agent users applying the guidance to normal coding work do not need `dist/skill.zip`.

Edit source files in the repository. Do not edit files inside `dist/skill.zip`.

When files under `skill/` change, rebuild `dist/skill.zip` so the optional ChatGPT Skill package stays synchronized. README-only and root-documentation-only changes do not require a package rebuild.

## Development workflow

1. Edit `skill/SKILL.md` only for core behavior.
2. Put detailed guidance in `skill/references/`.
3. Keep guidance language-agnostic.
4. Avoid numeric scoring.
5. Preserve the senior reviewer behavior.
6. Rebuild and verify the zip when files under `skill/` change.

## Optional ChatGPT package

These commands are for maintainers rebuilding the optional ChatGPT Skill package after files under `skill/` change.

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

No. This repository is primarily an instruction pack for coding agents. `dist/skill.zip` is an optional ChatGPT Skill package.

### Does this force overengineering?

No. The guidance rejects pattern abuse and prefers the smallest design that improves clarity, maintainability, testability, and change safety.

### Does it give code scores?

No. It uses concrete findings, refactoring guidance, and trade-offs instead of numeric scores.

### Does it work for any language?

Yes. The guidance is language-agnostic and expects agents to follow idioms of the language and ecosystem under review.

### What is the difference between `skill/` and `dist/skill.zip`?

`skill/` contains reusable guidance files that coding agents can read and the source packaged for ChatGPT. `dist/skill.zip` is the generated ChatGPT installable package; coding agents do not need it.

## License

MIT. See `LICENSE`.
