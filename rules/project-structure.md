# Generated AWS target structure

Generate infrastructure in `infra/`, CI/CD files for the PRD-selected provider, and operations material
in `ops/`. Modules own networking, edge, compute, PostgreSQL, Redis, storage, identity,
observability, backup, and budgets. Environment roots own development, staging, and production
composition and variables, never copied modules. Runbooks cover deployment, rollback, migration,
incident response, restore, and disaster recovery. Generate a root `.env.example` with the complete
local AWS variable names and obvious placeholders, and require `.env` in `.gitignore`. Never place
real credentials in `.env.example`, Git, state, saved plans, evidence, or application templates.
GitHub Actions is the default and uses `.github/workflows/`; GitLab CI uses `.gitlab-ci.yml`.
Both must provide executable CI, plan, immutable build, staging, protected production, rollback,
and drift jobs. Do not generate GitHub workflows for a GitLab-selected project.
