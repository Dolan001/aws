# AWS behavior pack

Code-free agents, skills, commands, hooks, rules, and deterministic structure contracts used by
`agents` to design, generate, validate, deploy, verify, and recover production AWS systems.

## When it is selected

An explicit `Deployment provider: AWS` PRD directive records the destination, but `$start-build`
still defers AWS work. Run `$start-deployment --deployment aws` only when you want deployment assets
and readiness checks. This selects the `aws` pack and generates infrastructure, CI/CD, operational
plans, and evidence in the target project. It does not apply infrastructure or deploy an app.

Live staging, production, and rollback are separate commands with explicit authorization,
environment boundaries, and readiness evidence. No build command pushes or mutates AWS by default.

The default path uses CloudFront, WAF, ALB, ECS Fargate, ECR, RDS PostgreSQL, ElastiCache Redis,
S3, the approved DNS provider, ACM, Secrets Manager, KMS, CloudWatch, and AWS Backup as required.
Nginx, Gunicorn,
Celery, WebSockets, SES, SNS, and EventBridge are selected only from verified application needs.
Route 53 is the default DNS provider; Cloudflare is optional when selected in the PRD.
Infrastructure and workflows are generated into the target monorepo, never copied from templates.

For local/manual deployment, generated projects include a `.env.example` containing
`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_REGION`, and optional `AWS_SESSION_TOKEN`.
Prefer an AWS profile or another short-lived session. If local variables are necessary, copy
`.env.example` to ignored `.env` and replace the placeholders. Add a scoped
`CLOUDFLARE_API_TOKEN` only when Cloudflare DNS changes are selected. GitHub Actions is the
default CI/CD provider and uses OIDC; GitLab CI is also supported and must use equivalent short-lived
federation and protected production approvals. Runtime services use IAM roles and Secrets Manager;
real credentials are never committed.

## What verification means

Readiness checks cover configuration, identity, supply chain, migration and rollback plans,
observability, backup and restore, and immutable release artifacts. Production promotion uses the
already verified staging digest and protected approval; a passing Terraform/OpenTofu format check
alone is not a deployment approval. Inspect `$deployment-status` and the target's `.ai/` evidence
before an operation.

`agents/` defines AWS roles, `skills/` the inspect/design/generate/verify/deploy/recover work,
`rules/` and `hooks/` the safety boundaries, and `commands/` the phase contracts. This repository
never stores generated infrastructure, state, plans, credentials, or cloud identifiers.
