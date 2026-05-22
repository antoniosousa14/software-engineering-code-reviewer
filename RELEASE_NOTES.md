# Software Engineering Code Reviewer v0.1.0

Initial release of Software Engineering Code Reviewer.

This repository provides an AI coding agent instruction pack for senior-level code review, refactoring, architecture guidance, and maintainability.

It is primarily designed for coding agents such as Codex, Claude Code, Cursor, Windsurf, Cline, Aider, Google Antigravity, and similar tools.

It also includes an optional ChatGPT Skill package at `dist/skill.zip`.

## Highlights

- Senior software engineering code review guidance.
- Refactoring guidance for turning prototype or messy code into maintainable code.
- Architecture-aware review using FURPS+, SOLID, GRASP, cohesion, coupling, encapsulation, and testability.
- Language-agnostic guidance for any programming language.
- Senior reviewer behavior by default.
- Mentor-style explanations only when explicitly requested.
- No numeric code scoring.
- Explicit avoidance of overengineering.
- Clear separation between:
  - AI coding agent usage through repository instructions.
  - Optional ChatGPT Skill installation through `dist/skill.zip`.

## Included guidance

- Review behavior
- Engineering review checklist
- FURPS+ quality lens
- Architecture principles
- Refactoring playbook
- Naming and style guidance
- Response templates

## Usage

For AI coding agents:

1. Read `AGENTS.md`.
2. Read the relevant agent-specific file:
   - `CODEX.md`
   - `CLAUDE.md`
   - `ANTIGRAVITY.md`
   - `CURSOR.md`
3. Use the focused reference files in `software-engineering-code-reviewer/references/` when needed.

For ChatGPT:

1. Download `dist/skill.zip`.
2. Upload/import it in ChatGPT's current Skills area.
3. Do not upload the full GitHub repository zip.

## Release asset

Attach:

`dist/skill.zip`

Do not attach the full repository zip as the skill package.
