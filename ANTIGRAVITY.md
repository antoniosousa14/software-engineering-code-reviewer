# Google Antigravity Instructions

Read `AGENTS.md` first.

## Usage mode

For Google Antigravity-style agents applying the guidance to coding work:

- Use repository files as instruction context.
- Google Antigravity does not install, pass, or consume `dist/skill.zip`.
- Maintain senior-reviewer behavior and language-agnostic guidance.

## Maintainer mode

When editing this repository:

- Treat repository files as the source of truth.
- Keep edits focused and easy to review.
- Preserve multi-agent compatibility.
- Rebuild and verify `dist/skill.zip` only when files under `software-engineering-code-reviewer/` change.
- Do not add platform-specific files unless they are useful to repository maintenance or skill distribution.

## Optional ChatGPT package

- Keep `software-engineering-code-reviewer/` as the only source for the optional ChatGPT Skill package.
