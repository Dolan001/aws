---
name: verify-aws-deployment
description: Independently verify generated AWS assets or an explicitly accessible deployed environment. Use for pre-deployment readiness, post-deployment checks, or deployment-status assessment.
---

# Verify AWS deployment

For generated assets, apply `rules/verification.md` and validate the complete structure contract,
HCL, workflows, identity, supply chain, database release safety, alarms, rollback, and recovery.
Remain read-only with respect to AWS.

For a live environment, require explicit read-only access and exact environment identity. Match the
running task definitions and image digests to approved evidence; verify health, API contracts,
critical journeys, queues, WebSockets, data operations, alarms, logs, metrics, backup status, and
deployment events. Record commands and results; do not repair or deploy during independent review.
