# API Approval Policy

## Purpose
Prevent unverified, commercially unsuitable, insecure, or unreliable APIs from entering production systems.

## Approval gates
An API remains `review_required` until all applicable gates have documented evidence:

1. **Identity and ownership** — provider identity and official domain verified.
2. **Functional fit** — exact endpoints, fields, geographic/entity coverage, freshness, and known gaps documented.
3. **Commercial/legal** — commercial use, redistribution, caching, attribution, derived data, and applicable restrictions checked against official terms.
4. **Cost** — free-tier limits, paid pricing, rate limits, overage, billing triggers, and realistic volume estimate documented.
5. **Security/privacy** — authentication, scopes, encryption, retention, training use, residency, subprocessors, and sensitive-data exposure assessed.
6. **Technical** — versioning, pagination, errors, uptime/SLA, SDKs, retries, timeouts, and integration effort assessed.
7. **Evidence** — repeatable tests completed with sanitized evidence and date.
8. **Operational ownership** — consuming project, owner, monitoring, fallback, and removal plan identified.

## Decision rules
- `approved`: all mandatory gates pass and an authorized human reviewer records the decision.
- `conditional`: only non-critical conditions remain; conditions and expiry must be explicit. Conditional is not production approval.
- `rejected`: a material requirement fails or risk is unacceptable.
- `not_reviewed`: default for new records.
- No API may be described as approved based only on discovery, vendor marketing, or a successful sample request.

## Change control
Re-review after material changes to pricing, terms, privacy, API version, ownership, coverage, or reliability. Record the date and evidence. Deprecate records when the provider withdraws the API or support ends.

## Secrets and data
Never store credentials or real customer/employee/beneficiary data here. Use synthetic or redacted test data only. Production secrets belong in the consuming project's approved secret manager.
