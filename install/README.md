# Install

This directory contains the first-pass installation automation for wiring the shared steering into agent-native locations.

## Commands

### `write-codex-config`

Write a baseline `config.toml` for Codex with conservative defaults and named profiles.

Example:

```bash
./install/install.sh write-codex-config --codex-dir ~/.codex
```

Behavior:
- Writes `~/.codex/config.toml` by default.
- Sets top-level defaults to `approval_policy = "untrusted"` and `sandbox_mode = "read-only"`.
- Adds `auto`, `readonly`, and `readonly_quiet` profiles for `codex --profile <name>`.
- Keeps `network_access = false` in `workspace-write` mode unless you later opt in.

### `write-project-entrypoint`

Generate a thin project-local wrapper for one agent that points back to this repository's canonical files and one selected profile overlay.

Supported agents:
- `codex`
- `claude`
- `kiro`

Example:

```bash
./install/install.sh write-project-entrypoint \
  --agent codex \
  --profile personal \
  --project-dir /path/to/project
```

Behavior:
- Writes `AGENTS.md` for Codex or Kiro projects.
- Writes `CLAUDE.md` for Claude projects.
- Refuses to overwrite an existing file unless `--force` is passed.

### `link-agent-skills`

Symlink all shared skills from this repository into a Codex, Claude, or Kiro skills directory.

Example:

```bash
./install/install.sh link-agent-skills --agent codex --agent-dir ~/.codex
./install/install.sh link-agent-skills --agent claude --agent-dir ~/.claude
./install/install.sh link-agent-skills --agent kiro --agent-dir ~/.kiro
```

Behavior:
- Creates `<agent-dir>/skills/` if needed.
- Links each `shared/skills/<name>` directory into `<agent-dir>/skills/<name>`.
- Refuses to overwrite an existing path unless `--force` is passed.

Compatibility aliases:
- `link-codex-skills`
- `link-claude-skills`
- `link-kiro-skills`

## Design Notes

- Installation stays simple and auditable.
- Generated wrappers are pointers back to this repository, not a second source of truth.
- Shared skills are linked as directories so updates in `shared/skills/` become visible immediately in Codex, Claude, and Kiro.
- Codex runtime security settings belong in `config.toml`; this repository can generate a baseline, but the active file lives under the user's Codex directory.

See `install/examples.md` for concrete commands.
