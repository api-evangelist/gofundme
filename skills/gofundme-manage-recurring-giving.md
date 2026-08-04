---
name: Monitor and reconcile GoFundMe Pro recurring giving
description: >-
  Read recurring donation plans at the organization, campaign and member level, walk their
  transaction and change history, and reprocess a failed recurring charge.
api: openapi/gofundme-pro-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - listOrganizationRecurringDonationPlans
  - listCampaignRecurringDonationPlans
  - listMemberRecurringDonationPlans
  - fetchRecurringDonationPlan
  - listRecurringDonationPlanTransactions
  - listRecurringDonationPlanHistory
  - listOrganizationRecurringDonationPlanHistory
  - reprocessRecurringDonationPlanTransaction
---

# Monitor and reconcile recurring giving

## 1. Authenticate

`POST https://api.classy.org/oauth2/auth`, `grant_type=client_credentials`, credentials in the body.
Bearer token, 3,600-second lifetime.

## 2. List the plans at the level you care about

- `listOrganizationRecurringDonationPlans` — `GET /organizations/{organization}/recurring-donation-plans`
- `listCampaignRecurringDonationPlans` — `GET /campaigns/{campaign}/recurring-donation-plans`
- `listMemberRecurringDonationPlans` — `GET /members/{member}/recurring-donation-plans`

Page with `page`/`per_page` (max 100). Narrow with `filter` and order with `sort`.

## 3. Read one plan and its ledger

- `fetchRecurringDonationPlan` — `GET /recurring-donation-plans/{recurring_donation_plan}`
- `listRecurringDonationPlanTransactions` — `GET /recurring-donation-plans/{recurring_donation_plan}/transactions`
- `listRecurringDonationPlanHistory` — `GET /recurring-donation-plans/{recurring_donation_plan}/history`

For an organization-wide change feed use
`listOrganizationRecurringDonationPlanHistory` — `GET /organizations/{organization}/recurring-donation-history`.

## 4. Reprocess a failed charge

`reprocessRecurringDonationPlanTransaction` —
`POST /recurring-donation-plans/{id}/transactions/{transaction_id}/reprocess`.

**This moves money.** There is no idempotency key on this operation and no sandbox to rehearse in.
Guard it:

1. Read the transaction first and confirm its status genuinely warrants a retry.
2. Record your own attempt log keyed on the transaction id before you call.
3. Never auto-retry on a timeout — re-read `listRecurringDonationPlanTransactions` and decide from
   the observed state.

## 5. React to changes in near-real time

Subscribe to `recurring_donation_plan.created` and `recurring_donation_plan.updated` webhooks rather
than polling; `updated` covers upgrades and cancellations. Verify the webhook secret on every
delivery. See `asyncapi/gofundme-webhooks.yml`.

## Errors

`403` on an unauthorized credential, `404` for a missing plan, `422` where a state-transition guard
blocks the operation. All plain JSON — see `errors/gofundme-problem-types.yml`.
