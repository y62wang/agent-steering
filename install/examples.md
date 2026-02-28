# Install Examples

## Codex project wrapper

```bash
./install/install.sh write-codex-config --codex-dir ~/.codex

./install/install.sh write-project-entrypoint \
  --agent codex \
  --profile personal \
  --project-dir /path/to/project

./install/install.sh link-agent-skills --agent codex --agent-dir ~/.codex
```

Writes:
- `~/.codex/config.toml`
- `/path/to/project/AGENTS.md`

Links:
- `~/.codex/skills/<skill-name>` -> `shared/skills/<skill-name>`

Useful launches:
- `codex --profile auto`
- `codex --profile trusted`
- `codex --profile yolo`
- `codex --profile readonly`

## Claude project wrapper plus shared skills

```bash
./install/install.sh write-project-entrypoint \
  --agent claude \
  --profile work \
  --project-dir /path/to/project

./install/install.sh link-agent-skills --agent claude --agent-dir ~/.claude
```

Writes:
- `/path/to/project/CLAUDE.md`

Links:
- `~/.claude/skills/<skill-name>` -> `shared/skills/<skill-name>`

## Kiro project wrapper plus shared skills

```bash
./install/install.sh write-project-entrypoint \
  --agent kiro \
  --profile work \
  --project-dir /path/to/project

./install/install.sh link-agent-skills --agent kiro --agent-dir ~/.kiro
```

Writes:
- `/path/to/project/AGENTS.md`

Links:
- `~/.kiro/skills/<skill-name>` -> `shared/skills/<skill-name>`
