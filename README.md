# agent-steering

Canonical repository for reusable agent steering, commands, and skills across Codex, Claude, and Kiro.

## Goals

- Keep one source of truth for shared instructions.
- Preserve each agent's native layout where practical.
- Support separate work and personal overlays without duplicating the whole repository.
- Keep installation concerns local to this repository for now.

## Layout

```text
agent-steering/
├── adapters/
│   ├── claude/
│   ├── codex/
│   └── kiro/
├── install/
├── profiles/
│   ├── personal/
│   └── work/
└── shared/
    ├── commands/
    ├── core/
    └── skills/
```

## Design

Shared guidance lives under `shared/`. Each agent adapter should stay thin and point back to shared content instead of re-encoding the same instructions in multiple places.

Recommended installation model:

- link or copy adapter files into agent-native locations
- keep agent-only features under the relevant adapter
- compose `shared/` plus one profile overlay for work or personal usage

## Agent Notes

### Codex

Use `AGENTS.md` as the primary steering entry point. Agent-specific runtime configuration still belongs in the user's Codex config.

### Claude

Use `CLAUDE.md` as the native entry point and keep Claude skills in `.claude/skills/`.

### Kiro

Use `AGENTS.md` for shared steering and keep Kiro-only agents and hooks under `.kiro/`.

## Next Steps

- add installation/bootstrap automation under `install/`
- decide how profiles should be selected during install
- add more skills and commands as they stabilize
