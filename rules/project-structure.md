# Generated AWS target structure

Generate infrastructure in `infra/`, GitHub Actions in `.github/workflows/`, and operations material
in `ops/`. Modules own networking, edge, compute, PostgreSQL, Redis, storage, identity,
observability, backup, and budgets. Environment roots own development, staging, and production
composition and variables, never copied modules. Runbooks cover deployment, rollback, migration,
incident response, restore, and disaster recovery. Do not store credentials, state, saved plans, or
application templates.
