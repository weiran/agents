# Agents

This repo is the shared home for Codex skills, agent guardrails, and lightweight helper scripts.

## Contents
- `AGENTS.md`: shared guardrails and tool list.
- `skills/`: Codex skills exported from the local install.
- `scripts/browser-tools.ts`: Chrome DevTools helper CLI.

## Pointer-Style AGENTS
- Shared guardrail text lives here: `AGENTS.md`.
- Downstream repos should start their `AGENTS.md` with: `READ ~/Projects/agents/AGENTS.md BEFORE ANYTHING (skip if missing).`
- Add repo-specific notes under the pointer line only if needed.
- When updating shared instructions, edit this repo and mirror to `~/AGENTS.md` if you use a global file.

## Syncing With Other Repos
- Treat this repo as the canonical mirror for shared guardrails and helper scripts.
- When helpers are edited elsewhere, copy the changes back here and keep downstream copies byte-identical.
- Keep scripts portable and free of repo-specific imports.

## Browser Tools (`scripts/browser-tools.ts`)
- What it is: a standalone Chrome DevTools helper inspired by Mario Zechner's "What if you don't need MCP?" article. It launches/inspects DevTools-enabled Chrome profiles, evaluates JS, captures screenshots, and can terminate helper processes.
- Usage: run with `ts-node scripts/browser-tools.ts --help` (or execute directly if `ts-node` is on PATH). Common commands include `start --profile`, `nav <url>`, `eval '<js>'`, `screenshot`, `search --content "<query>"`, `content <url>`, `inspect`, and `kill --all --force`.
- Rebuilding: this repo does not track a compiled binary. You can generate one with `bun build scripts/browser-tools.ts --compile --target bun --outfile bin/browser-tools`.
- Portability: the script has no repo-specific imports and detects Chrome sessions launched via `--remote-debugging-port` or `--remote-debugging-pipe`.
