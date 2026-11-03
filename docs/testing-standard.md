# API Testing Standard

## Principles
Test from low-cost and non-production environments first. Use synthetic data, redact secrets, and avoid load or destructive tests unless explicitly permitted by the provider.

## Minimum test matrix
- Authentication: valid, invalid, expired, and least-privilege credential behavior.
- Contract: required parameters, response schema, field types, nullability, and error formats.
- Coverage: representative positive and negative cases across target countries, makes/models/entities, and edge cases.
- Pagination: continuation, page boundaries, duplicate handling, and maximum page behavior.
- Limits: documented rate limits and safe handling of 429 responses; do not intentionally exhaust paid quotas.
- Reliability: timeout, retry/backoff, transient 5xx, and malformed response handling.
- Freshness: timestamp semantics, update frequency, and stale-data behavior.
- Security/privacy: transport security, scopes, data minimization, and no secret leakage in logs.
- Cost: estimate calls per business transaction and monthly volume; verify billing behavior.

## Evidence record
For every test capture:
- Date/time and environment.
- API/version and endpoint (never include credentials).
- Sanitized request shape and response sample or hash.
- Expected vs actual result.
- Latency where relevant, pagination/coverage observations, and limitations.
- Result: pass, fail, partial, or not_run.

## Acceptance
A test suite is not a vendor certification. Approval also requires commercial, privacy, security, and operational review. Record failed and partial results; do not omit inconvenient evidence.
