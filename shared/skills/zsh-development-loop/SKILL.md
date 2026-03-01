---
name: zsh-development-loop
description: Use this skill when the user wants an end-to-end workflow for developing, refactoring, or hardening zsh scripts and expects explicit validation steps beyond generic coding guidance. Trigger on requests for a zsh script development process, shell refactor workflow, zsh automation loop, or "edit, validate, debug, test, commit, review" guidance for `.zsh` or zsh-based scripts.
---

# Zsh Development Loop Skill

Use this skill to orchestrate zsh script work without collapsing shell-specific validation into generic "run tests" advice.

## Workflow

1. Start with the `task-management` skill to define the target behavior, refactor boundaries, and what counts as proof for the script change.
2. Before changing behavior, capture the current contract with characterization checks: representative invocations, expected stdout or stderr, exit codes, file side effects, environment requirements, and failure paths that must remain stable across the refactor.
3. Use the `code-implementation` skill to make the smallest reasonable script or function change, while keeping zsh-specific assumptions explicit with patterns such as `emulate -L zsh` in reusable function files when local option drift is a risk.
4. Run a fast static pass first: `zsh -n` for parse validation, then any repository lint or formatting tools that are actually configured. Treat syntax success as necessary but not sufficient.
5. Run the script in an isolated shell to avoid false confidence from local dotfiles or ambient environment state. Prefer a clean invocation such as `env -i HOME=\"$HOME\" PATH=\"$PATH\" zsh -f ./script.zsh ...`, then add only the variables the script truly needs.
6. When refactoring logic-heavy functions, add or run automated behavior tests. Prefer `ShellSpec` for sourced functions and assertion-heavy shell behavior, and use `Bats` or equivalent black-box command tests for CLI entrypoints, exit codes, and output contracts.
7. For debugging, reproduce the failing path with the same invocation shape, then switch to the `debugging` skill. Use targeted tracing such as `zsh -x`, `set -x`, `setopt SOURCE_TRACE`, temporary diagnostic prints, fixture directories, and fake `PATH` shims to isolate command resolution and side effects.
8. Repeat the edit -> parse check -> isolated execution -> automated regression test loop until the chosen checks pass or the exact blocker is known.
9. Use the `commit-prep` skill to remove accidental churn, keep behavior changes separate from mechanical refactors when possible, and make sure the commit message explains the contract preserved or changed.
10. Use the `review` skill on the final diff or commit to look for quoting bugs, word-splitting regressions, missing error handling, unsafe temporary-file patterns, and validation gaps.

## Validation Ladder

- Parse validity: `zsh -n` catches syntax and parse errors early.
- Clean startup: `zsh -f` verifies the script without user rc files.
- Clean environment: `env -i ...` exposes hidden dependencies on shell variables, aliases, functions, locale, or `PATH`.
- Behavioral regression checks: compare stdout, stderr, exit status, and filesystem changes against characterized examples.
- Error-path checks: deliberately simulate missing files, bad flags, command failures, permission errors, and partial pipeline failures.
- Refactor safety: characterize existing behavior before moving functions around, then rerun the same checks after each slice.

## Handoff Rules

- Do not claim a zsh refactor is verified if only `zsh -n` was run.
- Do not assume a script is portable to other shells unless the requirement says so.
- If linting is mentioned, distinguish zsh-aware checks from generic shell linting. `ShellCheck` is useful for Bourne-style subsets, but it is not proof that zsh-specific semantics are correct.
- If no automated test harness exists, leave a precise command list that covers normal paths, edge cases, and failure paths from a clean shell.

## Skill Routing

- Planning and sequencing: `shared/skills/task-management/SKILL.md`
- Script and function changes: `shared/skills/code-implementation/SKILL.md`
- Verification strategy and regression coverage: `shared/skills/testing/SKILL.md`
- Failure isolation and tracing: `shared/skills/debugging/SKILL.md`
- Commit shaping and message quality: `shared/skills/commit-prep/SKILL.md`
- Final defect-finding pass: `shared/skills/review/SKILL.md`

## Reference Sources

- Zsh documentation: `https://zsh.sourceforge.io/Doc/Release/Invocation.html`
- Zsh options reference: `https://zsh.sourceforge.io/Doc/Release/Options.html`
- ShellSpec: `https://github.com/shellspec/shellspec`
- Bats-core documentation: `https://bats-core.readthedocs.io/`
- ShellCheck: `https://www.shellcheck.net/`
