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

## Local Environment Setup

### 1) Prerequisites

Install the following locally:

- Node.js 20+
- pnpm 9+
- Python 3.12+
- uv
- Docker + Docker Compose (recommended for Postgres and local service orchestration)

### 2) Clone and enter the repository

```bash
git clone <your-fork-or-repo-url>
cd programming_showcase
```

### 3) Setup frontend workspace dependencies

```bash
pnpm install
```

### 4) Setup Python environment

```bash
uv venv
source .venv/bin/activate
uv sync
```

> On Windows PowerShell, activate with:
>
> ```powershell
> .venv\Scripts\Activate.ps1
> ```

### 5) Optional: environment variables

When API/worker implementation lands, configure a local env file:

```bash
cp .env.example .env
```

(If `.env.example` is not present yet, this step can be skipped for now.)

## Running the Project Locally (as implementation lands)

The scaffold is intentionally minimal. As app code is added in upcoming phases, use the following command pattern:

### Start frontend

```bash
pnpm --filter ./apps/web dev
```

### Start API

```bash
uv run --project apps/api uvicorn main:app --reload
```

### Start worker

```bash
uv run --project apps/worker python -m worker.main
```

### Start local infrastructure (recommended)

```bash
docker compose -f infra/docker/docker-compose.yml up -d
```

## Running Tests and Checks

### Python tests

```bash
uv run pytest
```

### Python lint/type checks

```bash
uv run ruff check .
uv run mypy .
```

### Frontend tests and lint/type checks

```bash
pnpm test
pnpm lint
pnpm typecheck
```

## Current Status

This commit establishes repository structure and baseline configuration. Feature implementation follows the task board in `docs/task-board.md`.
