# Signal Forge

Signal Forge is an interactive web product that showcases backend engineering through live, operable data pipeline scenarios.

This repository is a monorepo scaffold for the v1 implementation described in the technical spec.

## Monorepo Layout

```text
apps/
  web/
  api/
  worker/
packages/
  core/
  contracts/
  ui/
  domain-nyc-tlc/
data/
  seed/
  scenarios/
docs/
  architecture.md
  api-spec.md
  event-model.md
  domain-pack-spec.md
  task-board.md
infra/
  docker/
  scripts/
  github/
tests/
  integration/
  e2e/
```

## Tooling Decisions (v1 defaults)

- Python environment manager: **uv**
- Frontend package manager: **pnpm**
- Frontend data fetching: **TanStack Query** (to be wired in app implementation)
- Queue: in-process abstraction with persistence-backed run state
- Contracts: Python-first with TypeScript mirror definitions

## Getting Started

### Prerequisites

- Node.js 20+
- pnpm 9+
- Python 3.12+
- uv

### Install root JS dependencies

```bash
pnpm install
```

### Create Python virtual environment

```bash
uv venv
uv sync
```

## Current Status

This commit establishes repository structure and baseline configuration. Feature implementation follows the task board in `docs/task-board.md`.
