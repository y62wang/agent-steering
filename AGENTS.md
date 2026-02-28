# Agent Steering

This repository is the canonical source of shared steering for multiple AI agents.

## Use This Repository

- Prefer shared guidance under `shared/`.
- Treat agent-specific adapters as thin wrappers, not separate sources of truth.
- Use one profile overlay from `profiles/` for work or personal usage.

## Shared Guidance

- `shared/core/coding-standards.md`
- `shared/core/review-style.md`
- `shared/core/security.md`
- `shared/commands/review.md`
- `shared/commands/repo-bootstrap.md`

## Shared Skills

- `shared/skills/review/SKILL.md`
- `shared/skills/repo-bootstrap/SKILL.md`
- `shared/skills/prioritization/SKILL.md`
- `shared/skills/task-management/SKILL.md`
- `shared/skills/memory-maintenance/SKILL.md`
- `shared/skills/continuous-learning/SKILL.md`
- `shared/skills/skill-authoring/SKILL.md`
- `shared/skills/debugging/SKILL.md`
- `shared/skills/testing/SKILL.md`
- `shared/skills/code-implementation/SKILL.md`
- `shared/skills/commit-prep/SKILL.md`
- `shared/skills/documentation-maintenance/SKILL.md`

## Persistent Context

- `shared/context/session-memory.md`
- `shared/context/external-sources.md`

## Vendored References

- `external/README.md`

## Repository Rules

- Keep installation logic under `install/`.
- Keep new skills under `shared/skills/<name>/SKILL.md`.
- Do not duplicate broadly reusable instructions under agent-specific directories.
