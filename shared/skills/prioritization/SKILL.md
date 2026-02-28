---
name: prioritization
description: Use this skill when the user gives multiple possible tasks, a backlog, or an ambiguous goal and the agent needs to choose what to do first based on impact, risk, dependencies, and cost to validate.
---

# Prioritization Skill

Use this skill when there is more work than can be done at once.

## Workflow

1. Restate the objective and the concrete success condition.
2. Separate blockers, correctness risks, and prerequisite work from optional polish.
3. Rank work by user impact, risk reduction, dependency order, and speed of validation.
4. Prefer the smallest step that produces evidence or unblocks the next decision.
5. Record what is intentionally deferred so it does not disappear between sessions.

## Heuristics

- Do first: blockers, broken paths, irreversible risks, missing context, setup needed for later work.
- Do later: broad cleanup, speculative optimization, style churn, and refactors without immediate payoff.
- Escalate when two priorities conflict and the repository does not provide a clear tie-breaker.
