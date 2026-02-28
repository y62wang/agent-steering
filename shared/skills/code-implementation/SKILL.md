---
name: code-implementation
description: Use this skill when the task is to add or modify code and the agent needs a disciplined implementation workflow that respects repository conventions, minimizes churn, and keeps the change easy to review and verify.
---

# Code Implementation Skill

Use this skill for routine coding work where the main risk is careless execution rather than missing ideas.

## Workflow

1. Read the relevant code paths and infer the local design before editing.
2. Change the smallest surface area that can satisfy the requirement.
3. Preserve established naming, structure, and abstraction boundaries unless they are part of the problem.
4. Prefer clear control flow and explicit data handling over clever compression.
5. Keep the diff reviewable by separating functional changes from cleanup unless both are inseparable.
6. Verify the result with direct checks, then inspect the diff for unintended churn.

## Rules

- Do not start by rewriting large areas to fit a preferred style.
- Avoid speculative abstractions unless a real second use already exists.
- If a change forces a pattern decision, make the tradeoff explicit in the handoff.
