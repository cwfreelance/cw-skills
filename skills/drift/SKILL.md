---
name: drift
description: Run the repo's drift-check and fix what it finds — env templates, doc paths, and doc commands out of sync with reality. Use when the user invokes /drift, says "check for drift", or docs look stale.
---

# /drift

Uses [drift-check](https://github.com/cwfreelance/drift-check), a zero-dependency script that
finds docs and env templates that no longer match the code.

1. Run `node scripts/drift-check.mjs` from the repo root. If the repo has no copy, it hasn't
   adopted drift-check yet — fetch the script + config into `scripts/` and tune the config globs
   to the repo's layout:
   ```sh
   mkdir -p scripts
   curl -o scripts/drift-check.mjs https://raw.githubusercontent.com/cwfreelance/drift-check/main/drift-check.mjs
   curl -o scripts/drift-check.config.json https://raw.githubusercontent.com/cwfreelance/drift-check/main/drift-check.config.json
   ```
2. Fix each finding by editing the doc or the env template to match reality. The checklist IS
   the script output — generated from reality, nothing else to consult, nothing to rot.
3. **If the CODE is what's wrong** (the doc described intended behavior the code fails to
   deliver), do NOT silently align the doc — flag the finding and STOP for the operator.
4. Re-run until clean. Commit with a one-line summary per finding fixed.

Escape hatches when a finding is intentional: `drift-ignore` on the doc line, or the config's
`envIgnore` / `pathIgnore`. Full config reference is in the drift-check README.
