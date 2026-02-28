---
name: commit-prep
description: Use this skill when preparing changes for commit, handoff, or PR submission and the agent needs to clean the diff, verify the change, and summarize intent and residual risk clearly.
---

# Commit Prep Skill

Use this skill before creating a commit or handing off a completed change.

## Workflow

1. Inspect the diff for accidental edits, debug residue, generated noise, and unrelated churn.
2. Split the work into the smallest reasonable set of commits when the diff contains more than one concern, so each commit can stand on its own and be reviewed independently.
3. Verify each commit candidate with the most direct available checks: tests, lint, typecheck, build, or a manual reproduction path.
4. Confirm that filenames, comments, and user-facing messages match the final behavior.
5. Summarize what changed, why it changed, and what remains unverified.
6. Write a commit message that reflects intent and scope rather than a vague action.

## Rules

- Prefer one coherent commit for one concern, but do not bundle unrelated work just to minimize commit count.
- Use a specific subject line that names the user-visible or repository-level change.
- Add a commit body when it helps explain motivation, major contents, or verification.
- The commit body should usually cover:
  - why this change exists
  - the main pieces included
  - how it was verified, or what remains unverified
- If verification could not run, say so explicitly.
- Do not hide risky or incomplete work behind an overconfident summary.
