# pi-mom

MOM skills for [MOM (Memory Oriented Machine)](https://github.com/momhq/mom) on the Pi coding agent.

Installs MOM's user-invocable memory skills into Pi:

- `/mom-status` — check MOM health, Ledger stats, and vault watermark
- `/mom-project` — bind the current directory to a MOM project id for scoped memory
- `/mom-fold` — fold newly captured sessions into the markdown vault (end-of-session save)
- `/mom-rebuild` — rebuild the vault from scratch over the full captured history

## Installation

```bash
pi install npm:pi-mom
```

Or let `mom init` handle it automatically when it detects Pi in your project.

## Requirements

- [Pi coding agent](https://pi.dev) installed
- [MOM](https://github.com/momhq/mom) installed and on PATH

## How it works

MOM captures your Pi sessions in the background (via the `mom watch` daemon) and
folds them into a navigable markdown vault under `.mom/vault/`. These skills are
thin wrappers over MOM's CLI and the vault files — the agent reads the vault
directly with its file tools. There is no MCP server: as of MOM v0.50 memory is
delivered entirely through the per-project markdown vault and the always-loaded
context block.

The skill files here are kept byte-identical to the canonical copies in
[momhq/mom](https://github.com/momhq/mom/tree/main/skills) via
`scripts/verify-skills-sync.sh`.

## Related

- [MOM](https://github.com/momhq/mom) — the memory engine
- [pi-mlx-models](https://github.com/vmarinogg/pi-packages/tree/main/pi-mlx-models) — local MLX model launcher for Pi
