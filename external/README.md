# External Skill Sources

This directory vendors upstream public skill sources that informed the shared steering in this repository.

Purpose:
- Preserve the exact source material used during curation.
- Give future sessions local reference files to inspect without re-downloading them.
- Keep third-party material separate from the repository's own shared guidance and skills.

## Included Sources

### `anthropics-skills/`

Source:
- `https://github.com/anthropics/skills`

Why it is here:
- Official Anthropic skill examples and the strongest current reference point for skill structure and workflow patterns.
- Especially relevant local paths:
  - `external/anthropics-skills/skills/skill-creator/SKILL.md`
  - `external/anthropics-skills/skills/webapp-testing/SKILL.md`
  - `external/anthropics-skills/skills/frontend-design/SKILL.md`
  - `external/anthropics-skills/skills/mcp-builder/SKILL.md`

Popularity snapshot captured on 2026-02-28:
- 79,433 GitHub stars

### `playwright-skill/`

Source:
- `https://github.com/lackeyjb/playwright-skill`

Why it is here:
- Strong community example for browser automation and UI validation workflows.
- Relevant local path:
  - `external/playwright-skill/skills/playwright-skill/SKILL.md`

Popularity snapshot captured on 2026-02-28:
- 1,818 GitHub stars

### `metaskills-skill-builder/`

Source:
- `https://github.com/metaskills/skill-builder`

Why it is here:
- Focused reference for writing and improving skills, with useful guidance on metadata, structure, and progressive disclosure.

Popularity snapshot captured on 2026-02-28:
- 82 GitHub stars

## Notes

- These are vendored source snapshots, not submodules.
- `.git/` directories were intentionally removed after download so the parent repository can track these files normally.
- Treat upstream licenses and notices in these directories as authoritative for the third-party material.
