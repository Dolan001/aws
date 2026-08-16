---
name: verify-aws-disaster-recovery
description: Verify AWS backup coverage, restore isolation, recovery procedures, RPO, RTO, and evidence. Use during readiness review and scheduled disaster-recovery exercises.
---

# Verify AWS disaster recovery

1. Map every durable store and required configuration to backup, retention, encryption, ownership,
   restore dependency order, RPO, and RTO.
2. Verify RDS automated backups/PITR, S3 versioning and lifecycle, infrastructure reproducibility,
   secrets recovery process, image retention, and required cross-account or cross-region copies.
3. Restore only into an approved isolated exercise environment. Never overwrite production.
4. Validate schema, integrity, counts, constraints, representative reads/writes, application startup,
   object access, and recovery timing.
5. Record achieved RPO/RTO, gaps, cleanup ownership, and the next exercise. A backup without a tested
   restore is not verified recovery.
