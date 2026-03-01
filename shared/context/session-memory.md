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

## 2026-03-01: Development loop orchestration skill

Goal:
- Add a shared skill that captures the standard development loop without duplicating the detailed guidance already present in the implementation, testing, debugging, commit, and review skills.

Research and rationale:
- Local skill-authoring guidance and vendored skill references were reviewed first to keep the new skill thin, triggerable, and based on progressive disclosure.
- The chosen shape is an orchestration skill rather than a monolithic process document because this repository already has narrow reusable skills for each major phase.
- The workflow explicitly loops on build and unit-test failures through `debugging` plus `testing`, then hands off commit shaping to `commit-prep` and final defect hunting to `review`.

Repository changes made in this session:
- Added `shared/skills/development-loop/SKILL.md`.
- Updated `AGENTS.md` so the new skill is visible in the shared skill list.

Notes for later:
- If this orchestration pattern proves stable, consider adding eval prompts that test whether agents route correctly between `task-management`, `code-implementation`, `testing`, `debugging`, `commit-prep`, and `review`.

## 2026-03-01: Zsh development loop skill

Goal:
- Add a shared skill for zsh script development and refactoring that is parallel to the generic development loop but much more explicit about proving shell behavior actually still works.

Research and rationale:
- Reused the thin orchestration shape from `development-loop` instead of inventing a separate long-form shell guide.
- Checked zsh invocation and option references to ground the workflow in `zsh -n`, `zsh -f`, `xtrace`, `sourcetrace`, and related built-in validation paths.
- Pulled in ShellSpec and Bats as complementary test-tool references: ShellSpec for sourced-function behavior, Bats for black-box command execution, exit status, and output checks.
- Kept ShellCheck in the references as a supplemental lint source only, because syntax and lint success are not enough evidence for zsh-specific refactors.

Repository changes made in this session:
- Added `shared/skills/zsh-development-loop/SKILL.md`.
- Updated `AGENTS.md` so the new skill is listed in discovery.
- Updated `shared/context/external-sources.md` with the zsh and shell-testing primary sources used for the skill.

Notes for later:
- If shell-focused work becomes more common, consider a narrower testing reference or template fixture layout for temporary directories, fake `PATH` shims, and golden-output checks.
