# AWS behavior pack

This repository contains deployment behavior only. Never store runnable applications, generated
OpenTofu/Terraform, Dockerfiles, GitHub workflows, credentials, state, plans, or cloud identifiers
here. Agents generate those artifacts inside a separate target monorepo after application testing.

Planning and validation are read-only with respect to AWS. Cloud mutation requires an explicit
environment command, execution authorization, verified readiness evidence, immutable artifact
digests, bounded identity, and environment locking. Production additionally requires protected
environment approval. Never deploy from uncommitted source or mutable image tags.
