# Cursor / Windsurf / Cline / Aider Instructions

Read `AGENTS.md` first.

For editor-based coding agents:

- Use repository-wide context carefully.
- Avoid broad rewrites.
- Modify files under `skill/` when changing skill behavior.
- Use repository files as instruction context. Editor-based coding agents do not use `dist/skill.zip`.
- Keep docs and skill references synchronized.
- Preserve the compact `SKILL.md` plus modular references structure.
- Maintain "senior reviewer by default, mentor only when asked."
- Rebuild and verify `dist/skill.zip` only when packaged files under `skill/` change.
- Inspect zip contents before committing when the package is rebuilt.
