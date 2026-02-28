# External Sources

This file maps imported public skill sources to the local skills that should draw on them.

## Discovery Source

Skills Marketplace:
- `https://skillsmp.com/`
- `https://skillsmp.com/about`

Use it for:
- ecosystem discovery
- category scanning
- spotting which public repositories are broadly visible

Do not use it as the sole quality signal:
- As of 2026-02-28, SkillsMP says community ratings and usage statistics are still planned.
- Use GitHub repository metadata and direct source inspection to judge popularity and quality.

## Codex Documentation

Primary sources:
- `https://developers.openai.com/codex/security/`
- `https://developers.openai.com/codex/config-basic`
- `https://developers.openai.com/codex/config-sample`

Use for:
- sandbox and approval behavior
- `config.toml` layout and precedence
- baseline Codex security profile recommendations in install docs

Key points captured on 2026-02-28:
- `workspace-write` still protects `.git`, `.codex`, and `.agents` as read-only inside writable roots.
- Network access is off by default and must be enabled explicitly under `[sandbox_workspace_write]`.
- Codex supports named profiles in `config.toml`, selected with `codex --profile <name>`.

## Vendored Repositories

### Anthropic official skills

Local root:
- `external/anthropics-skills/`

Use for:
- baseline skill structure
- workflow design
- examples of progressive disclosure

Most relevant local files:
- `external/anthropics-skills/skills/skill-creator/SKILL.md`
- `external/anthropics-skills/skills/webapp-testing/SKILL.md`
- `external/anthropics-skills/skills/frontend-design/SKILL.md`
- `external/anthropics-skills/skills/mcp-builder/SKILL.md`

Popularity snapshot on 2026-02-28:
- 79,433 GitHub stars

### Community Playwright skill

Local root:
- `external/playwright-skill/`

Use for:
- browser automation patterns
- responsive and visual verification flows
- practical script execution patterns for web testing

Most relevant local file:
- `external/playwright-skill/skills/playwright-skill/SKILL.md`

Popularity snapshot on 2026-02-28:
- 1,818 GitHub stars

### Meta skill-builder

Local root:
- `external/metaskills-skill-builder/`

Use for:
- skill naming and descriptions
- progressive disclosure
- turning repeated workflows into portable skills

Most relevant local files:
- `external/metaskills-skill-builder/SKILL.md`
- `external/metaskills-skill-builder/reference/skill-best-practices.md`
- `external/metaskills-skill-builder/reference/metadata-requirements.md`

Popularity snapshot on 2026-02-28:
- 82 GitHub stars

## Local Skill Mapping

- `shared/skills/skill-authoring/SKILL.md`
  - draw from Anthropic `skill-creator` and `metaskills-skill-builder`
- `shared/skills/testing/SKILL.md`
  - draw from Anthropic `webapp-testing` and community `playwright-skill`
- `shared/skills/debugging/SKILL.md`
  - pair with `shared/skills/testing/SKILL.md` when the issue requires browser or runtime reproduction
- `shared/skills/documentation-maintenance/SKILL.md`
  - update `shared/context/session-memory.md` when a session discovers durable context
