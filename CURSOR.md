# Cursor / Windsurf / Cline / Aider Instructions

Read `AGENTS.md` first.

## Usage mode

For editor-based coding agents applying the guidance to coding work:

- Use repository files as instruction context.
- Editor-based coding agents do not install, pass, or consume `dist/skill.zip`.
- Maintain "senior reviewer by default, mentor only when asked."

## Maintainer mode

When editing this repository:

- Use repository-wide context carefully.
- Avoid broad rewrites.
- Modify files under `software-engineering-code-reviewer/` when changing skill behavior.
- Keep docs and skill references synchronized.
- Preserve the compact `SKILL.md` plus modular references structure.
- Rebuild and verify `dist/skill.zip` only when files under `software-engineering-code-reviewer/` change.

## Optional ChatGPT package

- Inspect zip contents before committing when the package is rebuilt.
