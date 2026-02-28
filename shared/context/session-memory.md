# Session Memory

This file captures durable context from recent repository work so a later session can recover intent without relying on chat history.

## 2026-02-28: Meta-skills expansion

Goal:
- Turn this repository from a scaffold into a reusable shared steering base for stronger agents and a better development process.
- Priorities requested by the user: memory, prioritization, task management, self-learning, skill creation/improvement, coding, debugging, style, commit quality, and code review.
- Additional constraint from the user: preserve progress in a file so future sessions can recover context after a disconnect.

Source review performed:
- SkillsMP homepage and about page were reviewed for ecosystem signal and marketplace maturity.
- Anthropic's official `anthropics/skills` repository was reviewed as the strongest quality anchor and a source of canonical skill patterns.
- Community examples surfaced during research were used as secondary signal only.
- Public source repositories were downloaded into `external/` so future sessions can inspect the exact files locally.

Key external findings:
- SkillsMP is useful for discovery and category trends, but as of February 28, 2026 it explicitly says community ratings and usage statistics are still planned. Do not treat SkillsMP as a source of stable ratings yet.
- SkillsMP currently highlights popularity sorting and says it filters marketplace entries with a minimum GitHub star threshold, so GitHub stars are the practical popularity proxy for now.
- Anthropic's official skills repository is highly popular and actively maintained, with 79,433 GitHub stars at time of review.
- Official Anthropic examples emphasize repeatable workflows more than narrow prompts. Relevant themes for this repo include skill creation, testing web apps, MCP/server integration, and documentable multi-step procedures.
- A notable community signal is the Playwright skill repository (`lackeyjb/playwright-skill`), which had 1,818 GitHub stars at review time, reinforcing that testing and browser validation are especially useful skill categories.
- A notable meta-skill signal is `metaskills/skill-builder`, which focuses on improving skill authoring and progressive disclosure patterns.

External sources downloaded into the repository:
- `external/anthropics-skills/`
- `external/playwright-skill/`
- `external/metaskills-skill-builder/`
- Each vendored directory had its `.git/` folder removed after download so the parent repository can track the files normally.

Repository changes made in this session:
- Upgraded existing skills to proper YAML-frontmatter format:
  - `shared/skills/review/SKILL.md`
  - `shared/skills/repo-bootstrap/SKILL.md`
- Added meta-skills:
  - `shared/skills/prioritization/SKILL.md`
  - `shared/skills/task-management/SKILL.md`
  - `shared/skills/memory-maintenance/SKILL.md`
  - `shared/skills/continuous-learning/SKILL.md`
  - `shared/skills/skill-authoring/SKILL.md`
- Added development-process skills:
  - `shared/skills/debugging/SKILL.md`
  - `shared/skills/testing/SKILL.md`
  - `shared/skills/code-implementation/SKILL.md`
  - `shared/skills/commit-prep/SKILL.md`
- Added documentation and continuity support:
  - `shared/skills/documentation-maintenance/SKILL.md`
  - `shared/context/external-sources.md`
  - `external/README.md`
- Added installation/bootstrap automation:
  - `install/install.sh`
  - `install/examples.md`
  - `install/README.md`
  - Installer now supports linking shared skills into Codex, Claude, and Kiro skill directories from the same canonical `shared/skills/` source.
- Updated top-level discovery files:
  - `AGENTS.md` now lists the shared skills.
  - `README.md` now states that reusable workflows belong in `shared/skills/` and `external/`.

Selection rationale:
- Keep this repository focused on portable, shared workflows rather than tool-specific clones of marketplace skills.
- Prefer skills that improve agent behavior across many repositories.
- Use official Anthropic patterns plus popularity signals from the ecosystem, but translate them into repository-agnostic guidance.

What still seems worthwhile later:
- Add more install flows for agent-specific extras beyond shared skills, especially Kiro `.kiro/agents/` and `.kiro/hooks/`.
- Consider a thin `documentation-maintenance` skill if repeated doc drift appears.
- Consider adding references or scripts only after a workflow proves repetitive enough to justify them.
