# Generated AWS target structure

Generate infrastructure in `infra/`, GitHub Actions in `.github/workflows/`, and operations material
in `ops/`. Modules own networking, edge, compute, PostgreSQL, Redis, storage, identity,
observability, backup, and budgets. Environment roots own development, staging, and production
composition and variables, never copied modules. Runbooks cover deployment, rollback, migration,
incident response, restore, and disaster recovery. Generate a root `.env.example` with the complete
local AWS variable names and obvious placeholders, and require `.env` in `.gitignore`. Never place
real credentials in `.env.example`, Git, state, saved plans, evidence, or application templates.
