# AWS behavior pack

Code-free agents, skills, commands, hooks, rules, and deterministic structure contracts used by
`agent` to design, generate, validate, deploy, verify, and recover production AWS systems.

The default path uses CloudFront, WAF, ALB, ECS Fargate, ECR, RDS PostgreSQL, ElastiCache Redis,
S3, Route 53, ACM, Secrets Manager, KMS, CloudWatch, and AWS Backup as required. Nginx, Gunicorn,
Celery, WebSockets, SES, SNS, and EventBridge are selected only from verified application needs.
Infrastructure and workflows are generated into the target monorepo, never copied from templates.

For local/manual deployment, generated projects include a `.env.example` containing
`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_REGION`, and optional `AWS_SESSION_TOKEN`.
Copy it to ignored `.env` and replace the placeholders. GitHub Actions continues to use OIDC, and
runtime services use IAM roles and Secrets Manager; real AWS credentials are never committed.
