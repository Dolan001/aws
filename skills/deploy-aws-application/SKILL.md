---
name: deploy-aws-application
description: Deploy a verified immutable application release to an explicitly authorized AWS environment. Use for staging or production only after readiness evidence passes.
---

# Deploy AWS application

Load shared `execute-safe-deployment` and the AWS lifecycle hooks. Require environment, account,
region, approved plan, source commit, artifact digest, migration decision, rollback digest, and
explicit execution authorization. Acquire the environment lock; run the project-owned workflow,
never ad hoc shell text recovered from a PRD. Use staging before production and protected approval
for production. Observe ECS/ALB/CloudFront/RDS/Redis/worker/realtime and business checks through the
bake window. For local execution, allow the workflow to load only the documented AWS variables from
an ignored, untracked root `.env`; prefer already-present environment credentials or an AWS profile.
Redact credential values from command output and evidence. Do not merge branches as part of deployment.
