# AWS generation rules

- Generate OpenTofu-compatible HCL with pinned providers, reusable modules, separate environment
  roots, encrypted versioned remote state, locking, and no committed state or plan files.
- Use at least two Availability Zones for production networking and managed data services unless an
  approved cost/availability decision says otherwise. Restrict security groups by source group.
- Use ACM TLS, Route 53, Secrets Manager references, KMS encryption, private buckets, CloudFront
  Origin Access Control, WAF managed protections, RDS backups/PITR, deletion protection, and log retention.
- Use GitHub OIDC with exact organization, repository, environment, and ref conditions. Separate
  read-only plan, staging deploy, and production deploy roles. Never generate access keys.
- Generate this root local-auth contract with placeholders only:
  `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_REGION`, and optional
  `AWS_SESSION_TOKEN`. Local deployment commands may load those names from an ignored, untracked
  `.env`; CI/CD must use OIDC and runtime workloads must use IAM roles.
- Build once, create SBOM/provenance, scan, push to ECR, and promote the same digest. Pin actions.
- Generate pull-request CI plus plan, image build, staging, production, rollback, and scheduled drift
  workflows. Production requires protected-environment approval and deployment concurrency.
- Make database migrations a singleton release task using expand/migrate/contract compatibility.
- Generate dashboards, actionable alarms, smoke checks, rollback and restore runbooks, and cost tags.
- Never run `apply`, update DNS, create credentials, or contact production during generation.
