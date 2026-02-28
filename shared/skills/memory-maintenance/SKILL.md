---
name: memory-maintenance
description: Use this skill when important context should persist beyond the current session, including durable decisions, repository conventions, recurring pitfalls, and environment facts that should be written down instead of left in chat history.
---

# Memory Maintenance Skill

Use this skill when the agent learns something that future sessions will need.

## Workflow

1. Distinguish durable facts from temporary observations.
2. Persist durable context in the repository artifact closest to where it matters: shared guidance, a command, a skill, or a profile overlay.
3. Keep active task state in `tasks/` using descriptive filenames, and reserve broader memory artifacts for durable context that should outlive the task itself.
4. Capture decisions, constraints, recurring commands, known pitfalls, and verification expectations.
5. Keep stored memory concise, factual, and easy to update.
6. Remove or revise stale memory when the repository proves it wrong.

## Heuristics

- Prefer repository memory over hidden conversational memory.
- Do not create notes for one-off incidents unless they reveal a reusable pattern.
- If the same clarification is needed twice, promote it into shared guidance.
- Update `shared/context/session-memory.md` when a session adds durable external research, structural decisions, or follow-up tasks that would be expensive to rediscover.
- Do not use `shared/context/session-memory.md` as the default home for in-progress task tracking when `tasks/` is the better fit.
