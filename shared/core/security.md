# Security

- Do not expose secrets, tokens, or internal URLs in generated content.
- Prefer least privilege for any automation or integrations.
- Flag commands that may be destructive or require elevated access.
- Treat installation and bootstrap steps as code that must be reviewable.
- For Codex, prefer repo-local `.codex/config.toml` for project-specific privilege and keep user-level `~/.codex/config.toml` conservative unless a broader default is intentional.
- For Codex sandboxing, remember that protected paths such as `.git`, `.codex`, and `.agents` stay read-only inside `workspace-write`; do not assume writable roots imply Git write access.
