# Agent Instructions

## Project purpose

This repository provides multi-agent guidance for senior software engineering code review and includes a ChatGPT Skill named `software-engineering-code-reviewer`. The guidance helps AI coding agents review, refactor, write, and improve code with senior software engineering standards across programming languages.

The packaged skill is instruction and reasoning guidance. It is not a code execution tool.

## Repository structure

- `skill/` is the skill source.
- `skill/SKILL.md` contains concise skill metadata and core behavior instructions.
- `skill/references/` contains detailed review, architecture, refactoring, naming, and response guidance.
- `skill/agents/openai.yaml` contains ChatGPT UI metadata.
- `dist/skill.zip` is generated from the contents of `skill/`.
- Outer repository files document the project and guide maintenance. They must not be packaged inside `dist/skill.zip`.

## Required behavior

- Preserve the senior-reviewer behavior.
- Keep `SKILL.md` concise.
- Move detailed guidance into `skill/references/`.
- Keep the skill language-agnostic.
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
4. Package the skill after changes.
5. Inspect the zip contents after packaging.
6. Confirm the zip root contains `SKILL.md`, `agents/openai.yaml`, and `references/*.md`.
7. Confirm the zip does not contain outer repository files.
8. Commit source changes and `dist/skill.zip` together.

## Packaging rules

- Do not use PowerShell `Compress-Archive` as the preferred packaging method because it can create zip entries with Windows backslash separators.
- Use the cross-platform Python zip method instead.
