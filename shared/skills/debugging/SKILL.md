---
name: debugging
description: Use this skill when behavior is broken, unexpected, flaky, or unclear and the agent needs a disciplined debugging loop to reproduce, isolate, instrument, fix, and verify the issue.
---

# Debugging Skill

Use this skill for failures, regressions, and unclear runtime behavior.

## Workflow

1. Reproduce the issue and capture the exact failing behavior.
2. Narrow the scope by identifying the smallest layer where expected and actual behavior diverge.
3. Add instrumentation, logs, or targeted checks before changing code blindly.
4. Form and test one hypothesis at a time until the cause is isolated.
5. Apply the smallest fix that addresses the cause, then verify with a direct reproduction path.
6. Add or strengthen a regression test when the project supports it.

## Rules

- Do not treat a plausible guess as a root cause.
- Prefer evidence from traces, inputs, and outputs over intuition.
- If the issue cannot be reproduced, focus on observability before refactoring.
