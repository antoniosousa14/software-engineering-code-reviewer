# Google Antigravity Instructions

Read `AGENTS.md` first.

For Google Antigravity-style agents:

- Treat repository files as the source of truth.
- Keep edits focused and easy to review.
- Preserve multi-agent compatibility.
- Use repository files as instruction context. Google Antigravity does not use `dist/skill.zip`.
- Keep `skill/` as the only source for the optional ChatGPT Skill package.
- Maintain senior-reviewer behavior and language-agnostic guidance.
- Rebuild and verify `dist/skill.zip` only when packaged files under `skill/` change.
- Do not add platform-specific files unless they are useful to repository maintenance or skill distribution.
