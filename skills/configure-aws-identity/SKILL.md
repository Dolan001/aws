---
name: configure-aws-identity
description: Generate and verify least-privilege AWS IAM and GitHub Actions OIDC trust boundaries. Use when creating AWS CI/CD roles or reviewing cloud deployment identity.
---

# Configure AWS identity

- Use GitHub OIDC and short-lived role sessions; never create access keys. Support an existing AWS
  access key pair only as a local/manual fallback loaded from an ignored, untracked `.env`.
- Restrict trust to the exact organization, repository, audience, environment, workflow/ref, and
  permitted event. Prevent untrusted pull requests from assuming privileged roles.
- Separate read-only validation/plan, artifact publication, staging deployment, production
  deployment, rollback, and runtime task roles.
- Scope actions and resources. Explain unavoidable wildcards and add conditions and permission boundaries.
- Keep task execution role separate from application task role. Reference secrets by ARN/name only.
- Generate `.env.example` with `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_REGION`, and
  optional `AWS_SESSION_TOKEN`, all with obvious placeholders. Require the real `.env` to remain
  ignored and untracked. Never copy its values into prompts, commands, logs, plans, or evidence.
- Validate policies and write identity evidence without tokens, credential material, or secret values.
