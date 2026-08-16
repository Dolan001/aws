# AWS verification rules

Independent verification must prove formatting, module initialization without remote state,
validation, static/security/policy checks, environment separation, no secrets/state/plans, bounded
IAM, pinned workflow actions, OIDC conditions, immutable image digests, protected production,
concurrency controls, migration serialization, health checks, autoscaling, alarms, log retention,
backup/PITR, rollback, and restore procedures.

When live environment verification is explicitly authorized, record account alias/ID, region,
environment, source commit, artifact digest, plan identity, deployment ID, health and smoke results,
alarm state, and timestamps without credentials or secret values. A successful command alone does
not prove availability, security, data integrity, realtime recovery, or rollback readiness.
