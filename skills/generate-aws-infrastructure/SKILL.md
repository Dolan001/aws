---
name: generate-aws-infrastructure
description: Generate modular environment-separated OpenTofu-compatible AWS infrastructure, CI/CD, observability, and runbooks in a target monorepo. Use after the AWS architecture is approved.
---

# Generate AWS infrastructure

Follow `rules/generation.md` and `rules/project-structure.md`.

1. Generate reusable modules and development, staging, and production roots with explicit inputs.
2. Configure encrypted versioned remote state and locking without committing backend credentials.
3. Generate only architecture-selected AWS services and least-privilege policies.
4. Generate pinned GitHub Actions for CI, plan, build, staging, production, rollback, and drift.
5. Generate alarms, dashboards, deployment, migration, rollback, incident, and recovery runbooks.
6. Run formatting, initialization without backend, validation, workflow, secret, security, and policy
   checks. Record exact results. Never run plan against an account or apply infrastructure.
