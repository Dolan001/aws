# Before AWS deployment

Require explicit environment execution authorization, readiness evidence, a reviewed unexpired
plan, short-lived identity, immutable digest, protected production approval, clean verified source,
backup status, rollback target, and an environment lock. If local `.env` authentication is used,
require the file to be ignored and untracked, require a complete key pair, and never print its values.
Fail closed on any mismatch.
