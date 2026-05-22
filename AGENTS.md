# Agent Instructions

## Project purpose

This repository is an AI coding agent instruction pack for senior software engineering code review, refactoring, architecture guidance, and maintainability. It helps AI coding agents review, refactor, write, and improve code with senior software engineering standards across programming languages.

The repository also includes an optional ChatGPT Skill package named `software-engineering-code-reviewer`. Coding agents use repository files as instruction context; they do not use `dist/skill.zip`.

## Repository structure

- `AGENTS.md` is the repository-wide instruction entry point for coding agents.
- `CODEX.md`, `CLAUDE.md`, `ANTIGRAVITY.md`, and `CURSOR.md` provide agent-specific repository guidance.
- `skill/SKILL.md` contains concise core behavior instructions that coding agents can read when useful and that ChatGPT uses in the optional Skill package.
- `skill/references/` contains detailed review, architecture, refactoring, naming, and response guidance.
- `skill/agents/openai.yaml` contains ChatGPT Skill UI metadata only. It is irrelevant to other coding agents.
- `dist/skill.zip` is the optional ChatGPT Skill package generated from the contents of `skill/`.
- Outer repository files document the project and guide maintenance. They must not be packaged inside `dist/skill.zip`.

## Required behavior

- Preserve the senior-reviewer behavior.
- Keep `SKILL.md` concise.
- Move detailed guidance into `skill/references/`.
- Keep the guidance language-agnostic.
- Do not add numeric scoring systems.
- Maintain "senior reviewer by default, mentor only when asked."
- Do not praise code just because it works.
- Prefer concrete improvements over abstract advice.
- Preserve behavior before refactoring.
- Avoid overengineering and pattern abuse.
- Avoid scripts unless they are absolutely necessary for maintenance.

## Change workflow

1. Read this file before editing.
2. Edit the smallest useful set of files.
3. Keep docs and skill references synchronized.
4. Rebuild the optional ChatGPT Skill package when packaged files under `skill/` change.
5. Inspect the zip contents after packaging.
6. Confirm the zip root contains `SKILL.md`, `agents/openai.yaml`, and `references/*.md`.
7. Confirm the zip does not contain outer repository files.
8. Commit packaged source changes and `dist/skill.zip` together when the package is rebuilt.

## Packaging rules

- Do not use PowerShell `Compress-Archive` as the preferred packaging method because it can create zip entries with Windows backslash separators.
- Use the cross-platform Python zip method instead.
