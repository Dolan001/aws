# Deploy AWS environment

Deploy only the explicitly named environment after readiness passes and execution is explicitly
authorized. Staging precedes production. Production requires protected approval. Promote immutable
digests, capture runtime evidence, and stop or roll back on declared abort signals.
