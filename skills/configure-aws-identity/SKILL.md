---
name: configure-aws-identity
description: Generate and verify least-privilege AWS IAM and GitHub Actions OIDC trust boundaries. Use when creating AWS CI/CD roles or reviewing cloud deployment identity.
---

# Configure AWS identity

- Use GitHub OIDC and short-lived role sessions; never create access keys.
- Restrict trust to the exact organization, repository, audience, environment, workflow/ref, and
  permitted event. Prevent untrusted pull requests from assuming privileged roles.
- Separate read-only validation/plan, artifact publication, staging deployment, production
  deployment, rollback, and runtime task roles.
- Scope actions and resources. Explain unavoidable wildcards and add conditions and permission boundaries.
- Keep task execution role separate from application task role. Reference secrets by ARN/name only.
- Validate policies and write identity evidence without tokens, credential material, or secret values.
