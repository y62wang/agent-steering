---
name: testing
description: Use this skill when implementing or changing behavior requires validation through tests, reproducible checks, browser verification, or regression coverage and the agent needs to choose the fastest credible way to prove the change works.
---

# Testing Skill

Use this skill whenever a change is not complete until behavior is verified.

## Workflow

1. Identify the narrowest test or check that can prove the target behavior.
2. Prefer existing test layers and project tooling before inventing new harnesses.
3. Match the test type to the risk: unit for logic, integration for boundaries, end-to-end or browser checks for real user flows.
4. Reproduce the bug or requirement before the fix when practical, then use the same path to verify the result.
5. Add regression coverage for bugs, edge cases, and assumptions likely to break again.
6. If full automation is not available, leave a precise manual verification path.

## Rules

- Do not claim a fix is verified if no check was actually run.
- Prefer fast local evidence first, then broader checks as needed.
- Keep new tests readable and targeted at behavior, not implementation trivia.

## Reference Sources

- For browser and local webapp validation patterns, read `external/anthropics-skills/skills/webapp-testing/SKILL.md`.
- For broader Playwright automation patterns, read `external/playwright-skill/skills/playwright-skill/SKILL.md`.
- Prefer borrowing the workflow shape from those sources rather than copying tool-specific commands blindly.
