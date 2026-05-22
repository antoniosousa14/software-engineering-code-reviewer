# Codex Instructions

Read `AGENTS.md` first.

For Codex-style agents:

- Modify files directly in this repository.
- Keep changes minimal, focused, and reviewable.
- Use this repository as coding-agent instruction context; do not use `dist/skill.zip` for Codex work.
- Read `skill/SKILL.md` and focused files in `skill/references/` when the task needs deeper guidance.
- Keep `SKILL.md` compact; put detailed behavior in `skill/references/`.
- Preserve senior-reviewer behavior and the "mentor only when asked" rule.
- Do not add numeric scoring systems.
- Rebuild and verify `dist/skill.zip` only when packaged files under `skill/` change.
- Create a clean commit message.
- Do not invent external installation facts without checking current official docs.

Optional ChatGPT package reminder:

```bash
mkdir -p dist
rm -f dist/skill.zip

python - <<'PY'
from pathlib import Path
from zipfile import ZipFile, ZIP_DEFLATED

root = Path("skill")
out = Path("dist/skill.zip")
out.parent.mkdir(exist_ok=True)

with ZipFile(out, "w", ZIP_DEFLATED) as zip_file:
    for path in root.rglob("*"):
        if path.is_file():
            zip_file.write(path, path.relative_to(root).as_posix())
PY
```

Inspect with `python -m zipfile -l dist/skill.zip`.
