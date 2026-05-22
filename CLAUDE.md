# Claude Code Instructions

Read `AGENTS.md` first.

## Usage mode

For Claude Code-style agents applying the guidance to coding work:

- Use repository files as instruction context.
- Claude Code does not install, pass, or consume `dist/skill.zip`.
- Maintain direct senior-reviewer behavior.
- Keep "mentor mode only on request" intact.
- Keep the guidance language-agnostic.

## Maintainer mode

When editing this repository:

- Preserve concise instructions.
- Do not over-expand `skill/SKILL.md`.
- Keep references modular and easy to load only when relevant.
- Avoid verbose theory and academic filler.
- Rebuild and verify `dist/skill.zip` only when files under `skill/` change.

## Optional ChatGPT package

- When rebuilding the zip, confirm it contains only the contents of `skill/`.
