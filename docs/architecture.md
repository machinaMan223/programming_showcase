# Architecture

Signal Forge architecture consists of:

- `apps/web`: Next.js frontend
- `apps/api`: FastAPI service
- `apps/worker`: pipeline worker runtime
- `packages/core`: platform abstractions and registries
- `packages/contracts`: canonical API + event contracts
- `packages/ui`: shared frontend components
- `packages/domain-nyc-tlc`: NYC TLC domain pack implementation
