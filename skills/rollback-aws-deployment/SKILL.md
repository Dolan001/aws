---
name: rollback-aws-deployment
description: Restore an AWS environment to a previously verified ECS task definition or artifact digest. Use only after an authorized rollback decision or automatic abort signal.
---

# Roll back AWS deployment

Load shared `rollback-deployment`. Confirm environment identity, current and target digests, target
task definitions, database compatibility, and authorization. Freeze deployments, preserve events
and logs, shift traffic using the tested ECS rollout mechanism, and wait for stable targets. Never
automatically reverse destructive PostgreSQL changes or restore data over newer writes. Verify the
same health, API, queue, realtime, data, and business checks used after deployment, then write
rollback evidence and incident follow-up.
