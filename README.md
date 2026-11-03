# API Intelligence Registry

A controlled, evidence-based registry for discovering, evaluating, testing, and approving external APIs before any production integration.

## Mission
Maintain one source of truth for API capabilities, coverage, commercial terms, operational limits, security/privacy posture, test evidence, approval state, alternatives, and consuming projects.

## Non-negotiable rules
- Discovery is not approval. A successful HTTP response is not sufficient evidence of production readiness.
- Never place API keys, tokens, passwords, personal data, or customer records in this repository.
- Do not connect an API to a production project until its record is reviewed and explicitly approved.
- Verify commercial-use rights, pricing, quotas, attribution, retention, and data-processing terms from authoritative sources.
- Record test date, environment, request shape (redacted), response evidence (sanitized), and limitations.
- Prefer free/no-cost validation first, but never assume a free tier permits commercial use.
- Keep this registry independent from ALHARIR, Merchant OS, and other production project data.

## Lifecycle
`discovered → researching → testing → review_required → approved | rejected | deprecated`

Only an authorized human reviewer may set `approved`. Re-evaluate approval when pricing, terms, API versions, ownership, or data handling changes.

## Repository map
- `registry/apis.json`: curated API inventory; remains empty until candidates complete review.
- `registry/discovery/public-apis/`: imported discovery-only snapshot split into JSON shards; see `manifest.json` and `docs/attribution-public-apis.md`.
- `schema/api-record.schema.json`: machine-readable record contract.
- `templates/api-record.template.json`: starter record.
- `docs/approval-policy.md`: approval gates and governance.
- `docs/testing-standard.md`: repeatable technical validation.
- `docs/priority-domains.md`: research priorities.

## Adding an API
1. Create a record from the template.
2. Cite official documentation, pricing, terms, and privacy sources.
3. Mark unknowns explicitly; do not infer them.
4. Run the applicable tests and attach sanitized evidence.
5. Complete security, privacy, legal/commercial, and operational review.
6. Keep status at `review_required` until an authorized reviewer approves it.

## Imported discovery catalog
The community-maintained `public-apis/public-apis` HTTP API category tables are imported under `registry/discovery/public-apis/`. This is discovery metadata only: upstream descriptions and Auth/HTTPS/CORS flags are not independently verified. Pricing, commercial rights, coverage, privacy, security, and endpoint availability remain unverified. See the manifest and attribution document.

## Current state
No APIs are approved. The curated inventory remains empty until individual candidates complete evidence collection and human review.
