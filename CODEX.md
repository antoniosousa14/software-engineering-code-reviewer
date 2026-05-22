# Codex Instructions

Read `AGENTS.md` first.

For Codex-style agents:

- Modify files directly in this repository.
- Keep changes minimal, focused, and reviewable.
- Treat `skill/` as the source of truth for the ChatGPT Skill.
- Keep `SKILL.md` compact; put detailed behavior in `skill/references/`.
- Preserve senior-reviewer behavior and the "mentor only when asked" rule.
- Do not add numeric scoring systems.
- Package the skill after changes.
- Verify `dist/skill.zip` contents before finishing.
- Create a clean commit message.
- Do not invent external installation facts without checking current official docs.

Packaging reminder:

```powershell
New-Item -ItemType Directory -Force dist
Compress-Archive -Path skill\* -DestinationPath dist\skill.zip -Force
tar -tf dist\skill.zip
```
