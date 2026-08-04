---
name: Sync GoFundMe Pro transactions and supporters into a CRM
description: >-
  Keep an external CRM or data warehouse in step with GoFundMe Pro by subscribing to the webhook
  events and reconciling with paged reads of transactions, transaction items and supporters.
api: openapi/gofundme-pro-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - listOrganizationTransactions
  - listOrganizationTransactionItems
  - listOrganizationSupporters
  - fetchTransaction
  - fetchSupporter
  - listTransactionItems
  - listTransactionReceipts
---

# Sync transactions and supporters into a CRM

## 1. Subscribe to the events first

Configure webhooks in GoFundMe Pro → Apps & Integrations → Webhooks → Endpoints → Add Endpoint.
Delivery is Svix-backed. Subscribe to:

- `transaction.created`, `transaction.updated`
- `supporter.created`, `supporter.updated`
- `recurring_donation_plan.created`, `recurring_donation_plan.updated`

Rules the endpoint must satisfy:

- Public HTTPS endpoint accepting `POST` with a JSON body.
- Return a `2xx` **within 15 seconds** — acknowledge immediately and process asynchronously, or the
  event counts as unprocessed.
- **Validate the webhook secret from the request headers on every delivery.** Do not trust an
  unverified payload.
- Failures retry on progressive backoff; five days of repeated failure deactivates the endpoint.
- Maximum 50 endpoints per account.

Only three resources emit events. Campaigns, fundraising pages, fundraising teams, registrations,
payouts and designations have **no** webhook — those still need polling. See
`asyncapi/gofundme-webhooks.yml`.

## 2. Backfill and reconcile with paged reads

- `listOrganizationTransactions` — `GET /organizations/{organization}/transactions`
- `listOrganizationTransactionItems` — `GET /organizations/{organization}/transaction-items`
- `listOrganizationSupporters` — `GET /organizations/{organization}/supporters`

Use `sort=created_at` for a stable ascending walk, `page`/`per_page` (max 100) to page, and
`filter=created_at>2026-01-01T00:00:00.000Z` (operand URL-encoded) for an incremental window.
Datetimes are ISO 8601 `YYYY-MM-DDTHH:mm:ss.sssZ`.

## 3. Hydrate rather than fan out

Use `with=` to include related resources in the same response — for example
`?with=supporter,designation,campaign` — instead of issuing one call per row. Use `fields=` to trim
the payload to the columns your CRM actually stores. This is the single biggest lever against the
rate limit.

## 4. Per-record detail when you need it

- `fetchTransaction` — `GET /transactions/{transaction}`
- `fetchSupporter` — `GET /supporters/{supporter}`
- `listTransactionItems` — `GET /transactions/{transaction}/items` (multi-item Giving Cart orders)
- `listTransactionReceipts` — `GET /transactions/{transaction}/receipts`

## Reconciliation notes

- `transaction.updated` fires for refunds and status changes — treat updates as authoritative and
  re-read rather than patching your copy from the event alone.
- The webhook service aggregates duplicate/rapid events, so do not assume one event per change;
  make your consumer idempotent on transaction id + updated timestamp.

## Rate limits

1,800 requests/minute per application, signalled by `X-RateLimit-Limit`, `X-RateLimit-Remaining`,
`X-RateLimit-Reset` and, on `429`, `Retry-After` plus `retry_after` in the body.

## Related artifacts

`conventions/gofundme-conventions.yml`, `errors/gofundme-problem-types.yml`,
`rate-limits/gofundme-rate-limits.yml`, `data-model/gofundme-data-model.yml`.
