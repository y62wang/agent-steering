# Security

- Do not expose secrets, tokens, or internal URLs in generated content.
- Prefer least privilege for any automation or integrations.
- Flag commands that may be destructive or require elevated access.
- Treat installation and bootstrap steps as code that must be reviewable.
- For Codex, prefer `workspace-write` with explicit profile-based approvals over ad hoc launch flags, and reserve bypass modes for deliberate high-trust sessions.
- For Codex sandboxing, remember that protected paths such as `.git`, `.codex`, and `.agents` stay read-only inside `workspace-write`; do not assume writable roots imply Git write access.
