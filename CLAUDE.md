# Claude Code Instructions

Read `AGENTS.md` first.

For Claude Code-style agents:

- Preserve concise instructions.
- Do not over-expand `skill/SKILL.md`.
- Keep references modular and easy to load only when relevant.
- Avoid verbose theory and academic filler.
- Maintain direct senior-reviewer behavior.
- Keep "mentor mode only on request" intact.
- Keep the guidance language-agnostic.
- Use repository files as instruction context. Claude Code does not use `dist/skill.zip`.
- Rebuild and verify `dist/skill.zip` only when packaged files under `skill/` change.
- When rebuilding the zip, confirm it contains only the contents of `skill/`.
