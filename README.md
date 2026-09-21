# cw-skills

My Claude Code subagents and skills.

## Install

Drop a file into the matching directory under `~/.claude/`:

- **Agents** (subagents) → `~/.claude/agents/`
- **Skills** → `~/.claude/skills/<name>/SKILL.md`

```sh
cp agents/fixer.md ~/.claude/agents/
cp -r skills/drift ~/.claude/skills/
```

Restart Claude Code (or start a new session) to pick it up.

## Contents

### Agents

- [`fixer`](agents/fixer.md) — escalation fixer for a stuck adversarial-review → fix loop on a branch or PR. Does one round per activation, then stops and reports. Uses `model: fable` and `effort: xhigh` by default, tweak if needed. Also uses `/codex:adversarial-review` by default; override it in your project's `CLAUDE.md` if you review differently.

### Skills

- [`drift`](skills/drift/SKILL.md) — `/drift` runs [drift-check](https://github.com/cwfreelance/drift-check), a zero-dependency script that finds docs and env templates out of sync with the code, then fixes what it reports. If the repo doesn't have the script yet, the skill fetches it.
