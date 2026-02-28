---
name: repo-bootstrap
description: Use this skill when creating, bootstrapping, or restructuring a repository and the agent needs to establish a clean layout, shared guidance, and thin tool-specific adapters.
---

# Repository Bootstrap Skill

Use this skill when setting up or reorganizing a repository.

## Workflow

1. Inspect the current workspace, git state, and existing conventions before creating structure.
2. Prefer a standard, reviewable layout with minimal custom machinery.
3. Keep shared guidance separate from installation, generated files, and tool-specific adapters.
4. Add the smallest viable scaffolding first, then fill in reusable commands and skills as patterns stabilize.
5. Document entry points so later sessions can discover the structure without rereading the whole repository.
