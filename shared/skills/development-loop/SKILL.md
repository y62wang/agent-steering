---
name: development-loop
description: Use this skill when the user wants an end-to-end development workflow or asks to automate the normal coding loop, including implementation, build, unit tests, fixing failures, preparing a commit, and reviewing the result. Trigger on requests for a development process, coding pipeline, implementation loop, or "build, test, fix, commit, review" style workflows even when the user does not name this skill explicitly.
---

# Development Loop Skill

Use this skill to orchestrate a full development pass without re-explaining the detailed guidance that already exists elsewhere in this repository.

## Workflow

1. Start with the `task-management` skill to define done criteria, sequence the work, and keep one active step at a time.
2. Use the `code-implementation` skill to make the required code changes with the smallest reasonable diff.
3. Use the `testing` skill to identify and run the most direct build and unit-test checks that can validate the change.
4. If the build or unit tests fail, switch to the `debugging` skill to reproduce the failure, isolate the cause, apply the smallest fix, and then return to the `testing` skill to rerun the same checks.
5. Repeat the implement -> build/test -> debug/fix loop until the target checks pass or the exact blocker is known.
6. Use the `commit-prep` skill to inspect the diff, remove accidental churn, confirm commit boundaries, and prepare a truthful commit message.
7. Create the commit only after the chosen verification steps are complete, unless the user explicitly wants an earlier checkpoint commit.
8. Use the `review` skill on the final diff or commit to look for correctness issues, regressions, security risks, and missing tests before handoff.
9. If review finds problems, return to `code-implementation`, `debugging`, and `testing` as needed, then refresh the commit plan. Do not amend an existing commit unless the user explicitly asks for that history shape.

## Handoff Rules

- Keep this skill thin: rely on the referenced skills for detailed execution guidance.
- Name which step is currently active so the user can see where the loop stands.
- Do not claim the work is complete if build or unit-test evidence is missing.
- If a required build or unit-test command cannot be found, say so explicitly and fall back to the nearest credible verification path using the `testing` skill.
- If the user asks for only one phase, use the narrower underlying skill instead of forcing the whole loop.

## Skill Routing

- Planning and sequencing: `shared/skills/task-management/SKILL.md`
- Code changes: `shared/skills/code-implementation/SKILL.md`
- Build and unit-test verification: `shared/skills/testing/SKILL.md`
- Failure investigation and fix loop: `shared/skills/debugging/SKILL.md`
- Commit shaping and message quality: `shared/skills/commit-prep/SKILL.md`
- Final review pass: `shared/skills/review/SKILL.md`
