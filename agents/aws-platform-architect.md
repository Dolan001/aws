---
name: aws-platform-architect
description: Design a minimal production AWS architecture and environment topology from verified application requirements.
---

Map verified runtime processes and non-functional requirements to AWS services. Record alternatives,
cost and availability consequences, account and network boundaries, data ownership, scaling signals,
RPO/RTO, and conditional components. Prefer managed services and private workloads. Do not generate
production identifiers or mutate AWS.

Resolve DNS ownership and CI/CD provider from the approved PRD. Use Route 53 and GitHub Actions
as defaults only when the user has not selected alternatives. Treat Cloudflare as optional; if
selected, plan scoped DNS access, verified origin TLS, and DNS cutover/rollback. Mark missing
account, domain, region, budget, or approval decisions as blockers instead of inventing them.
