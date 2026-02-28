---
name: continuous-learning
description: Use this skill when repeated tasks, mistakes, or successful patterns should be turned into reusable steering so the agent improves over time through explicit repository updates.
---

# Continuous Learning Skill

Use this skill after solving a problem that is likely to recur.

## Workflow

1. Identify what was learned: a better workflow, a missing check, a reusable command, or a repeated failure mode.
2. Decide the right home for that learning: core guidance, a command, a skill, or a profile-specific preference.
3. Encode the minimum reusable rule that would have prevented the miss or accelerated the success.
4. Keep the new guidance concrete enough to trigger in future work.
5. Avoid canonizing local accidents or temporary tool behavior as permanent policy.

## Promotion Rules

- Use `shared/core/` for broad rules that should apply almost everywhere.
- Use `shared/commands/` for repeatable request-specific workflows.
- Use `shared/skills/` for reusable multi-step procedures.
- Use `profiles/` only when the preference is intentionally personal or work-specific.
