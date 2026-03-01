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
- Trusted repo-local `.codex/config.toml` files override `~/.codex/config.toml`; project config precedence is below CLI flags and profiles but above user config.

## Git Commit Guidance

Primary sources:
- `https://git-scm.com/docs/SubmittingPatches`
- `https://git-scm.com/docs/git-add`
- `https://git-scm.com/docs/MyFirstContribution`

Use for:
- modular commit boundaries
- partial staging workflows
- commit message structure and rationale

Key points captured on 2026-02-28:
- Git's own contribution guidance says to make separate commits for logically separate changes.
- If the explanation for one commit grows too long, that is usually a signal to split the change into finer-grained commits.
- `git add -p` and `git add -e` are the core tools for staging only the hunks that belong in the next commit.
- Commit messages should explain the problem and why the chosen change is better, not just restate the diff.
- Git's contributor tutorial recommends a short subject line, a blank line, and a body that supplies the "why" that is not obvious from the patch.

## Task Tracking Guidance

Primary sources:
- `https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/about-task-lists`
- `https://docs.github.com/en/issues/tracking-your-work-with-issues/planning-and-tracking-work-for-your-team-or-project`
- `https://www.atlassian.com/agile/project-management/backlog-refinement-meeting`

Use for:
- breaking larger work into smaller tracked tasks
- making progress and blockers visible
- keeping active task lists current and actionable

Key points captured on 2026-02-28:
- GitHub task lists are meant to break larger work into smaller trackable tasks with visible completion state.
- GitHub's planning guidance emphasizes explicit tracked work and visible blocking relationships.
- Atlassian's backlog refinement guidance emphasizes regular review, reprioritization, and removing stale items so the backlog stays actionable.
- For local `tasks/` files, the practical equivalent is one current task note per work item, explicit blockers, and frequent refresh of next actions.

## Zsh Script Validation Guidance

Primary sources:
- `https://zsh.sourceforge.io/Doc/Release/Invocation.html`
- `https://zsh.sourceforge.io/Doc/Release/Options.html`
- `https://github.com/shellspec/shellspec`
- `https://bats-core.readthedocs.io/`
- `https://www.shellcheck.net/`

Use for:
- zsh-specific parse, startup, and tracing options
- choosing behavior-test tooling for shell refactors
- clarifying where generic shell linting helps and where it does not prove zsh behavior

Key points captured on 2026-03-01:
- `zsh -n` is the fast parse gate, but it does not validate runtime behavior, environment assumptions, or side effects.
- `zsh -f` is valuable for refactors because it disables user startup files and exposes hidden dependencies on local shell configuration.
- The `xtrace` and `sourcetrace` options are the core built-in tracing aids when reproducing command flow and sourced-file execution.
- ShellSpec is a good fit for testing sourced shell functions and assertion-heavy shell behavior; Bats is a good fit for black-box CLI tests that validate exit status and output.
- ShellCheck is useful for Bourne-style shell pitfalls, but it should be treated as a supplemental lint layer rather than proof that zsh-specific code is correct.

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
- `shared/skills/task-tracking/SKILL.md`
  - draw from GitHub task list guidance and backlog refinement practices for maintaining actionable local task files
- `shared/skills/zsh-development-loop/SKILL.md`
  - draw from zsh invocation and options docs plus ShellSpec, Bats, and ShellCheck references for shell-specific validation strategy
