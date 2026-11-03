---
name: configure-aws-identity
description: Generate and verify least-privilege AWS IAM and CI/CD federation trust boundaries. Use when creating AWS deployment roles or reviewing cloud deployment identity.
---

# Configure AWS identity

- Use short-lived role sessions with the selected CI/CD provider's federation; never create access
  keys. GitHub Actions uses OIDC by default. Support an existing AWS
  access key pair only as a local/manual fallback loaded from an ignored, untracked `.env`.
- Restrict trust to the exact organization, repository, audience, environment, workflow/ref, and
  permitted event where the provider supports them. Prevent untrusted pull requests from assuming
  privileged roles. If equivalent trust restrictions are unavailable, block deployment readiness.
- Separate read-only validation/plan, artifact publication, staging deployment, production
  deployment, rollback, and runtime task roles.
- Scope actions and resources. Explain unavoidable wildcards and add conditions and permission boundaries.
- Keep task execution role separate from application task role. Reference secrets by ARN/name only.
- Generate `.env.example` with `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_REGION`, and
  optional `AWS_SESSION_TOKEN`, all with obvious placeholders. Require the real `.env` to remain
  ignored and untracked. Never copy its values into prompts, commands, logs, plans, or evidence.
- If Cloudflare is selected, add only `CLOUDFLARE_API_TOKEN=<placeholder>` to `.env.example`
  for optional local deployment. Use a scoped CI/CD secret or equivalent short-lived credential
  for automated DNS changes; never place token values in the PRD or generated infrastructure.
- Validate policies and write identity evidence without tokens, credential material, or secret values.
