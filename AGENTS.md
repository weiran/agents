# Personal Codex Guidance

## Working Style

- Lead with the outcome or findings. Keep communication concise and direct.
- Inspect the real implementation and available evidence before explaining or changing behavior.
- Fix root causes and keep changes tightly scoped to the requested task.
- Follow existing project patterns and avoid unrelated refactoring.
- When instructions conflict, call out the conflict and take the safer path.

## Changes And Verification

- Use the repository's existing package manager, runtime, and documented workflows.
- Preserve unrelated worktree changes and inspect `git status` and relevant diffs before editing.
- Add regression tests for bugs when practical.
- Update current documentation when public behavior, APIs, routes, deployment, or workflows change.
- Prefer end-to-end verification. If blocked, run the closest useful checks and state the exact gap.
- Check current maintenance, release activity, and adoption before adding a production dependency.

## Git And Machine Safety

- Never run destructive Git operations or delete or rename unexpected files without explicit approval.
- Use `trash` for intentional local deletions when available.
- Branch changes, pushes, force operations, history rewrites, and amends require an explicit request.
- Stage only task-owned files or hunks. Commit only when requested or required by repository guidance.
- Use Conventional Commits unless the repository specifies another convention.
- Never re-sign an application, ad-hoc sign it, or change its bundle identifier for debugging without explicit approval.
