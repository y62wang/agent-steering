---
name: task-tracking
description: Use this skill when work should be tracked in a `tasks/` file across multiple updates or sessions and the agent needs a disciplined way to keep the task note current, prioritized, and easy to resume.
---

# Task Tracking Skill

Use this skill when a task file under `tasks/` should act as the durable source of current status for an active work item.

## Workflow

1. Create or reuse one descriptive file under `tasks/` for the active work item.
2. Start the note with the goal, key constraints, and what counts as done.
3. Keep a short ordered task list with one active item at a time.
4. Record blockers, dependencies, and open questions explicitly instead of implying them through prose.
5. Update the note when scope, priority, verification status, or the next action changes.
6. Prefer concise status snapshots over narrative logs; keep only the information needed for the next session to resume quickly.
7. When work pauses, end with the exact next step, relevant files, checks run, and anything still unverified.

## Recommended Task Note Shape

- Title and goal
- Constraints and assumptions
- Ordered steps with status markers
- Current blocker or risk, if any
- Files touched or likely touch points
- Verification run
- Next action

## Rules

- Keep the task file focused on one work item; split unrelated efforts into separate task files.
- Use descriptive filenames that identify the task without opening the file.
- Update the existing task file instead of creating near-duplicate notes for the same work.
- Prefer current truth over historical completeness; remove stale bullets when they no longer reflect the plan.
- If priorities change, reorder the steps instead of leaving obsolete sequencing in place.
- Do not let the task note drift away from the actual repository state.

## Source Notes

- GitHub task list guidance reinforces breaking larger work into smaller tracked tasks and making progress visible.
- Agile backlog refinement guidance reinforces regular reprioritization, removal of stale items, and keeping the backlog actionable.
