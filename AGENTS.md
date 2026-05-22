# Agent Instructions

## Project purpose

This repository is an AI coding agent instruction pack for senior software engineering code review, refactoring, architecture guidance, and maintainability. It helps AI coding agents review, refactor, write, and improve code with senior software engineering standards across programming languages.

The repository also includes an optional ChatGPT Skill package named `software-engineering-code-reviewer`. Coding agents use repository files as instruction context; they do not use `dist/skill.zip`.

## Repository structure

- `AGENTS.md` is the repository-wide instruction entry point for coding agents.
- `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, and `CURSOR.md` provide agent-specific repository guidance.
- `software-engineering-code-reviewer/SKILL.md` contains concise core behavior instructions that coding agents can read when useful and that ChatGPT uses in the optional Skill package.
- `software-engineering-code-reviewer/references/` contains detailed review, architecture, refactoring, naming, and response guidance.
- `software-engineering-code-reviewer/agents/openai.yaml` contains ChatGPT Skill UI metadata only. It is irrelevant to other coding agents.
- `dist/skill.zip` is the optional ChatGPT Skill package generated from the contents of `software-engineering-code-reviewer/`.
- Outer repository files document the project and guide maintenance. They must not be packaged inside `dist/skill.zip`.

## Usage mode

When applying this guidance to normal coding work:

- Use Markdown files in this repository as instruction context.
- Start with `AGENTS.md` and the relevant agent-specific file.
- Read `software-engineering-code-reviewer/SKILL.md` and focused files in `software-engineering-code-reviewer/references/` when deeper guidance is useful.
- Do not install, pass, or consume `dist/skill.zip` in coding agents.
- Ignore `software-engineering-code-reviewer/agents/openai.yaml`; it is ChatGPT Skill metadata only.

## Required behavior

- Preserve the senior-reviewer behavior.
- Keep `SKILL.md` concise.
- Move detailed guidance into `software-engineering-code-reviewer/references/`.
- Keep the guidance language-agnostic.
- Do not add numeric scoring systems.
- Maintain "senior reviewer by default, mentor only when asked."
- Do not praise code just because it works.
- Prefer concrete improvements over abstract advice.
- Preserve behavior before refactoring.
- Avoid overengineering and pattern abuse.
- Avoid scripts unless they are absolutely necessary for maintenance.

## Maintainer mode

When editing this repository:

1. Read this file before editing.
2. Edit the smallest useful set of files.
3. Keep docs and skill references synchronized.
4. Rebuild the optional ChatGPT Skill package when files under `software-engineering-code-reviewer/` change.
5. Inspect the zip contents after packaging.
6. Confirm the zip root contains `SKILL.md`, `agents/openai.yaml`, and `references/*.md`.
7. Confirm the zip does not contain outer repository files.
8. Commit source changes under `software-engineering-code-reviewer/` and `dist/skill.zip` together when the package is rebuilt.

README-only and root-documentation-only changes do not require rebuilding `dist/skill.zip`.

## Optional ChatGPT package

- Do not use PowerShell `Compress-Archive` as the preferred packaging method because it can create zip entries with Windows backslash separators.
- Use the cross-platform Python zip method instead.
