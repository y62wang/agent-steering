---
name: skill-authoring
description: Use this skill when creating, refining, or reorganizing a skill and the agent needs to write strong trigger language, concise workflows, and supporting references without duplicating broader guidance.
---

# Skill Authoring Skill

Use this skill when adding or improving a skill in this repository.

## Workflow

1. Start from the task pattern the skill should capture, not from a generic topic label.
2. Write trigger language that makes it obvious when the skill should activate.
3. Keep the main workflow short, procedural, and biased toward decisions the base model would not reliably infer.
4. Put detailed variants, references, or scripts next to the skill only when they materially reduce repeated work.
5. Avoid duplicating broad rules that already belong in `shared/core/` or agent-specific adapters.

## Quality Bar

- A good skill changes behavior, not just wording.
- A good skill is reusable across sessions, not tied to one ticket.
- A good skill is cheap to load and easy to maintain.

## Reference Sources

- For canonical official patterns, read `external/anthropics-skills/skills/skill-creator/SKILL.md`.
- For stronger metadata and structure guidance, read `external/metaskills-skill-builder/SKILL.md`.
- For deeper detail, use `shared/context/external-sources.md` to find the most relevant imported reference file.
