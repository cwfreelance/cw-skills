# cw-skills

My Claude Code subagents and skills.

## Install

Drop a file into the matching directory under `~/.claude/`:

- **Agents** (subagents) → `~/.claude/agents/`
- **Skills** → `~/.claude/skills/`

```sh
cp agents/fixer.md ~/.claude/agents/
```

Restart Claude Code (or start a new session) to pick it up.

## Contents

### Agents

- [`fixer`](agents/fixer.md) — escalation fixer for a stuck adversarial-review → fix loop on a branch or PR. Does one round per activation, then stops and reports. Set the review command on line ~66 for your project before use.
