---
name: documentation-maintenance
description: Use this skill when repository documentation, persistent notes, or operating guidance need to be created or updated so future sessions inherit accurate context, workflows, and constraints instead of relearning them from chat history.
---

# Documentation Maintenance Skill

Use this skill when durable written context matters as much as the immediate code change.

## Workflow

1. Identify which facts are durable enough to belong in repository documentation.
2. Update the narrowest file that future sessions are likely to read first.
3. For in-progress work or handoff state, prefer a descriptive task file under `tasks/` over burying the status in a broad context document.
4. Prefer operational details, decisions, constraints, and verification steps over narrative recap.
5. Keep docs synchronized with the current repository structure and tooling.
6. When work spans a session boundary, record the goal, sources used, files changed, and unresolved follow-ups.

## Preferred Homes

- `AGENTS.md` for top-level entry points and discovery.
- `README.md` for repository structure and operating model.
- `tasks/` for active task tracking and handoff notes with descriptive filenames.
- `shared/context/session-memory.md` for durable session context and research summaries.
- `shared/core/` when a documented rule should apply broadly.
- `shared/skills/` when the repeated pattern is procedural enough to be a skill.

## Rules

- Do not create sprawling status logs that duplicate git history.
- Remove or revise stale guidance when it no longer matches the codebase.
- If future sessions would likely ask "why was this done?", answer it in the repository.
