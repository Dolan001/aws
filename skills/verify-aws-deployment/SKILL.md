---
name: verify-aws-deployment
description: Independently verify generated AWS assets or an explicitly accessible deployed environment. Use for pre-deployment readiness, post-deployment checks, or deployment-status assessment.
---

# Verify AWS deployment

For generated assets, apply `rules/verification.md` and validate the complete structure contract,
HCL, workflows, identity, supply chain, database release safety, alarms, rollback, and recovery.
Require the separate CI/CD pack's independent verification evidence and confirm its provider,
artifact digest contract, protected production gate, and environment identity match AWS plans.
Remain read-only with respect to AWS.

For a live environment, require explicit read-only access and exact environment identity. Match the
running task definitions and image digests to approved evidence; verify health, API contracts,
critical journeys, queues, WebSockets, data operations, alarms, logs, metrics, backup status, and
deployment events. Check the chosen DNS provider, public HTTPS certificate, and origin TLS path;
verify staging and production use the intended account and region. Record commands and results;
do not repair or deploy during independent review.
