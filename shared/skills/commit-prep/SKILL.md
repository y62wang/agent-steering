---
name: commit-prep
description: Use this skill when preparing changes for commit, handoff, or PR submission and the agent needs to clean the diff, verify the change, and summarize intent and residual risk clearly.
---

# Commit Prep Skill

Use this skill before creating a commit or handing off a completed change.

## Workflow

1. Inspect the diff for accidental edits, debug residue, generated noise, and unrelated churn.
2. Split the work into the smallest reasonable set of logically separate commits so each commit has one main purpose and can be reviewed independently.
3. If one commit message needs to explain multiple unrelated concerns, treat that as a sign the work should probably be split further.
4. Use the index deliberately to shape commit boundaries: stage by path when whole files belong together, and use partial staging such as `git add -p` or `git add -e` when one file contains more than one concern.
5. Verify each commit candidate with the most direct available checks: tests, lint, typecheck, build, or a manual reproduction path.
6. Confirm that filenames, comments, and user-facing messages match the final behavior.
7. Summarize what changed, why it changed, and what remains unverified.
8. Write a commit message that reflects intent and scope rather than a vague action.

## Rules

- Prefer one coherent commit for one concern, but do not bundle unrelated work just to minimize commit count.
- A good modular commit should leave the tree in a sensible state on its own, or make any temporary coupling explicit in the message.
- Before committing, ask whether a reviewer could describe the commit in one sentence without using "and then also".
- Split mechanical renames, formatting-only churn, refactors, behavior changes, and documentation updates unless one depends directly on another.
- Order modular commits so earlier commits establish prerequisites and later commits build on them.
- Use a specific subject line that names the user-visible or repository-level change.
- Prefer an imperative subject line and keep it short enough to scan quickly.
- Add a commit body when it helps explain motivation, major contents, or verification.
- The commit body should usually cover:
  - why this change exists
  - the main pieces included
  - how it was verified, or what remains unverified
- If needed, mention alternatives considered or constraints that forced the chosen shape.
- Review the staged diff before committing; the commit should match the story told by its message.
- If verification could not run, say so explicitly.
- Do not hide risky or incomplete work behind an overconfident summary.

## Quick Checks

- Each staged commit candidate answers one primary question.
- The staged diff excludes unrelated cleanup and leftover experiments.
- The commit message still fits the staged diff after a final `git diff --cached` review.
