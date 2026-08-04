---
name: Record offline donations against a GoFundMe Pro campaign
description: >-
  Create supporter records and offline transaction records in bulk against a GoFundMe Pro campaign —
  the flow behind the official bulk-offline-donations Postman collection — and acknowledge them.
api: openapi/gofundme-pro-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - listOrganizationSupporters
  - createOrganizationSupporter
  - createCampaignTransaction
  - fetchTransaction
  - createAcknowledgement
  - listAcknowledgements
  - createTransactionDedication
---

# Record offline donations

> **There is no sandbox.** GoFundMe Pro issues one set of production credentials per app — no test
> mode, no test keys, no test tenant. Running this flow with real credentials **permanently adds
> transaction data** to the organization and campaign. Rehearse against the Postman mock server
> environment first (`sandbox/gofundme-sandbox.yml`), then run it for real, deliberately.

## 1. Authenticate

`POST https://api.classy.org/oauth2/auth` with `grant_type=client_credentials`. Send the token as
`Authorization: Bearer <access_token>`. Tokens live 3,600 seconds.

## 2. Resolve or create the supporter

- `listOrganizationSupporters` — `GET /organizations/{organization}/supporters`. De-duplicate before
  writing: filter on the donor's email with the `filter` parameter
  (`filter=email_address=someone@example.com`, operand URL-encoded).
- `createOrganizationSupporter` — `POST /organizations/{organization}/supporters` only when no
  matching supporter exists.

## 3. Create the offline transaction

`createCampaignTransaction` — `POST /campaigns/{campaign}/transactions`. For external requests this
creates an **offline** transaction record. Confirm with `fetchTransaction` —
`GET /transactions/{transaction}`.

## 4. Optional enrichment

- `createTransactionDedication` — `POST /transactions/{transaction}/dedications` for in-honor-of /
  in-memory-of gifts.
- `createAcknowledgement` — `POST /transactions/{transaction}/acknowledgements` to mark the donor as
  formally thanked; `listAcknowledgements` reads them back.

## Idempotency — read this before retrying

`POST` is **not** idempotent on this API, and there is **no** global `Idempotency-Key` header. A
retried create makes a second transaction. The only operation with an idempotency contract is the
scoped-magic-link batch endpoint, which takes an `idempotency_key` in its body — that mechanism is
not available here.

Safe pattern: assign your own external reference to each row, and before every create, query for an
existing transaction that carries it. Never blind-retry a `createCampaignTransaction` that timed
out — read back first. See `conventions/gofundme-conventions.yml`.

## Rate limits and batching

1,800 requests/minute per application. For a large import, pace writes, honour `Retry-After` on a
`429`, and process in chunks with a resume marker so a partial failure does not replay completed
rows.

## Errors

- `400` — malformed payload; the body carries `errors[]` of strings.
- `403` — the credential is not authorized for this campaign or organization.
- `404` — the campaign, organization or supporter does not exist.
- `422` — the payload is well-formed but violates a constraint.

See `errors/gofundme-problem-types.yml`.

## Reference

- https://github.com/classy-org/postman-collections/tree/main/bulk-offline-donations
