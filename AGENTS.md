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

## Repository Rules

- Keep installation logic under `install/`.
- Keep new skills under `shared/skills/<name>/SKILL.md`.
- Do not duplicate broadly reusable instructions under agent-specific directories.
