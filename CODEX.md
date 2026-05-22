# Codex Instructions

Read `AGENTS.md` first.

## Usage mode

For Codex-style agents applying the guidance to coding work:

- Use this repository as coding-agent instruction context.
- Do not install, pass, or consume `dist/skill.zip`.
- Read `software-engineering-code-reviewer/SKILL.md` and focused files in `software-engineering-code-reviewer/references/` when the task needs deeper guidance.
- Preserve senior-reviewer behavior and the "mentor only when asked" rule.
- Do not add numeric scoring systems.

## Maintainer mode

When editing this repository:

- Modify files directly in this repository.
- Keep changes minimal, focused, and reviewable.
- Keep `SKILL.md` compact; put detailed behavior in `software-engineering-code-reviewer/references/`.
- Preserve senior-reviewer behavior and the "mentor only when asked" rule.
- Do not add numeric scoring systems.
- Rebuild and verify `dist/skill.zip` only when files under `software-engineering-code-reviewer/` change.
- Create a clean commit message.
- Do not invent external installation facts without checking current official docs.

## Optional ChatGPT package

Use this package flow only when files under `software-engineering-code-reviewer/` change:

```bash
mkdir -p dist
rm -f dist/skill.zip

python - <<'PY'
from pathlib import Path
from zipfile import ZipFile, ZIP_DEFLATED

root = Path("software-engineering-code-reviewer")
out = Path("dist/skill.zip")
out.parent.mkdir(exist_ok=True)

with ZipFile(out, "w", ZIP_DEFLATED) as zip_file:
    for path in root.rglob("*"):
        if path.is_file():
            zip_file.write(path, path.relative_to(root).as_posix())
PY
```

Inspect with `python -m zipfile -l dist/skill.zip`.
