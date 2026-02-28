---
name: review
description: Use this skill when the user asks for a code review, PR review, or audit of recent changes and expects bug finding, regression analysis, risk assessment, and missing-test checks instead of implementation work.
---

# Review Skill

Use this skill when the task is to review rather than write code.

## Workflow

1. Inspect the diff, changed files, and the surrounding call paths before judging a line in isolation.
2. Prioritize correctness, regressions, security, data loss, and missing validation over style preferences.
3. Treat each finding as a claim that needs evidence from code, behavior, or a missing test.
4. Report findings first, ordered by severity, with concrete file references and a short explanation of impact.
5. After findings, list assumptions or unanswered questions, then give a short residual-risk summary.
