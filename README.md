# Agents

Based on the structure and guardrails from https://github.com/steipete/agent-scripts.

This repo is the version-controlled home for personal Codex guidance, skills, and lightweight helper scripts.

## Contents
- `AGENTS.md`: personal guidance installed globally through `~/.codex/AGENTS.md`.
- `skills/`: Codex skills exported from the local install.
- `scripts/browser-tools.ts`: Chrome DevTools helper CLI.

## Global AGENTS.md

- This repository's `AGENTS.md` is the canonical, version-controlled source for personal guidance.
- Symlink it to `~/.codex/AGENTS.md` so Codex loads it automatically in every repository:

  ```bash
  ln -s ~/Projects/agents/AGENTS.md ~/.codex/AGENTS.md
  ```

- Repository `AGENTS.md` files should contain only repository-specific guidance. Codex automatically layers them after the global file.

## Syncing With Other Repos
- Treat this repo as the canonical source for personal guidance and helper scripts.
- When helpers are edited elsewhere, copy the changes back here and keep downstream copies byte-identical.
- Keep scripts portable and free of repo-specific imports.

## Browser Tools (`scripts/browser-tools.ts`)
- What it is: a standalone Chrome DevTools helper inspired by Mario Zechner's "What if you don't need MCP?" article. It launches/inspects DevTools-enabled Chrome profiles, evaluates JS, captures screenshots, and can terminate helper processes.
- Usage: run with `ts-node scripts/browser-tools.ts --help` (or execute directly if `ts-node` is on PATH). Common commands include `start --profile`, `nav <url>`, `eval '<js>'`, `screenshot`, `search --content "<query>"`, `content <url>`, `inspect`, and `kill --all --force`.
- Rebuilding: this repo does not track a compiled binary. You can generate one with `bun build scripts/browser-tools.ts --compile --target bun --outfile bin/browser-tools`.
- Portability: the script has no repo-specific imports and detects Chrome sessions launched via `--remote-debugging-port` or `--remote-debugging-pipe`.
