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
├── external/
└── shared/
    ├── commands/
    ├── context/
    ├── core/
    └── skills/
```

## Design

Shared guidance lives under `shared/`. Each agent adapter should stay thin and point back to shared content instead of re-encoding the same instructions in multiple places.

Shared skills also live under `shared/skills/` so reusable workflows can improve over time without being trapped in one agent's local setup.

Vendored third-party references live under `external/` so the repository can keep upstream examples and supporting files without mixing them into the canonical shared guidance.

Recommended installation model:

- link or copy adapter files into agent-native locations
- keep agent-only features under the relevant adapter
- compose `shared/` plus one profile overlay for work or personal usage

## Agent Notes

### Codex

Use `AGENTS.md` as the primary steering entry point. Agent-specific runtime configuration still belongs in the user's Codex config.

This repository includes `install/install.sh write-codex-config` to generate a baseline `~/.codex/config.toml` with a higher-trust default plus named profiles. The generated default uses `workspace-write`, `on-request` approvals, and network access enabled. Protected paths such as `.git` still remain read-only in `workspace-write`; only the explicit `yolo` profile switches to `danger-full-access`.

### Claude

Use `CLAUDE.md` as the native entry point and keep Claude skills in `.claude/skills/`.

### Kiro

Use `AGENTS.md` for shared steering and keep Kiro-only agents and hooks under `.kiro/`.

## Next Steps

- decide how profiles should be selected during install
- keep promoting repeated workflows into shared skills and commands as they stabilize
