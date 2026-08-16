# AWS AI behavior pack

Code-free agents, skills, commands, hooks, rules, and deterministic structure contracts used by
`ai_workflow` to design, generate, validate, deploy, verify, and recover production AWS systems.

The default path uses CloudFront, WAF, ALB, ECS Fargate, ECR, RDS PostgreSQL, ElastiCache Redis,
S3, Route 53, ACM, Secrets Manager, KMS, CloudWatch, and AWS Backup as required. Nginx, Gunicorn,
Celery, WebSockets, SES, SNS, and EventBridge are selected only from verified application needs.
Infrastructure and workflows are generated into the target monorepo, never copied from templates.
