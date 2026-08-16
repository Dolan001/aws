---
name: design-aws-architecture
description: Design AWS accounts, networking, edge, runtimes, data services, identity, observability, scaling, cost, and recovery. Use after target inspection and before generating AWS infrastructure.
---

# Design AWS architecture

1. Map verified web, API, mobile-supporting API, worker, scheduler, and realtime processes.
2. Select only requirement-backed components using `rules/architecture.md`; explicitly decide
   CloudFront behaviors, ALB routes, ECS services, RDS, Redis, S3, identity, monitoring, and backup.
3. Keep Nginx and Gunicorn conditional. Record why any conditional service or package is needed.
4. Define account/environment isolation, VPC/AZ topology, security groups, encryption, secrets,
   scaling signals, availability, RPO/RTO, cost assumptions, alarms, rollout, and rollback.
5. Write `docs/deployment/aws-architecture.md` and architecture evidence. Do not generate or apply IaC.
