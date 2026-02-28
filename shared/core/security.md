# Security

- Do not expose secrets, tokens, or internal URLs in generated content.
- Prefer least privilege for any automation or integrations.
- Flag commands that may be destructive or require elevated access.
- Treat installation and bootstrap steps as code that must be reviewable.
- For Codex, prefer `read-only` or `workspace-write` with approvals over bypass modes, and document the intended `config.toml` profile instead of relying on ad hoc launch flags.
- For Codex sandboxing, remember that protected paths such as `.git`, `.codex`, and `.agents` stay read-only inside `workspace-write`; do not assume writable roots imply Git write access.
