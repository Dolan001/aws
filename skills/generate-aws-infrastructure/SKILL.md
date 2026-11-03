---
name: generate-aws-infrastructure
description: Generate modular environment-separated OpenTofu-compatible AWS infrastructure, CI/CD, observability, and runbooks in a target monorepo. Use after the AWS architecture is approved.
---

# Generate AWS infrastructure

Follow `rules/generation.md` and `rules/project-structure.md`.

1. Generate reusable modules and development, staging, and production roots with explicit inputs.
2. Configure encrypted versioned remote state and locking without committing backend credentials.
3. Generate only architecture-selected AWS services and least-privilege policies.
4. Expose scoped deployment roles and environment outputs to the CI/CD contract without writing
   provider pipeline files; the CI/CD pack owns those files.
5. Generate alarms, dashboards, deployment, migration, rollback, incident, and recovery runbooks.
6. Run formatting, initialization without backend, validation, secret, security, and policy
   checks. Record exact results. Never run plan against an account or apply infrastructure.
7. When Cloudflare is selected, generate scoped DNS/TLS integration and verified origin HTTPS;
   otherwise use the approved DNS provider. Keep DNS cutover an explicit deployment operation.
