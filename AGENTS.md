# Signal Forge Agent Instructions

## Mission
Build Signal Forge as an extensible interactive systems platform. Treat dataset-specific logic as domain-pack code, not platform code.

## Constraints
- Do not hard-code `nyc_tlc` assumptions into platform modules.
- Use typed models for API and event payloads.
- Prefer small, verifiable changes.
- Add or update tests for every behavior change.
- Keep file and package boundaries clean.

## Workflow
- Before major changes, restate the files you intend to touch.
- After code changes, run relevant tests, linters, and type checks.
- If a requirement is ambiguous, implement the smallest extensible version.
- Document new public interfaces in `docs/`.

## Code Quality
- Avoid hidden magic and surprising abstractions.
- Favor composition over inheritance.
- Keep functions and classes narrowly scoped.
- Do not introduce new dependencies without a clear need.
