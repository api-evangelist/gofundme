---
name: Read GoFundMe Pro campaign progress and build a leaderboard
description: >-
  Authenticate against the GoFundMe Pro API, read a campaign's fundraising progress, and rank its
  fundraising pages and teams to drive a progress bar or leaderboard on an external site. This is
  the flow GoFundMe Pro's own sample apps demonstrate.
api: openapi/gofundme-pro-api-openapi.json
generated: '2026-08-04'
method: generated
operations:
  - listOrganizationCampaigns
  - fetchCampaign
  - listCampaignFundraisingPages
  - listCampaignFundraisingTeams
  - fetchFundraisingPageOverview
  - fetchFundraisingTeamOverview
---

# Read campaign progress and build a leaderboard

## Prerequisites

- A GoFundMe Pro app with a `client_id` and `client_secret` (GoFundMe Pro → Apps & Integrations → API).
- The organization id you are reading.

## 1. Get an application access token

`POST https://api.classy.org/oauth2/auth` with `grant_type=client_credentials`, `client_id` and
`client_secret` in the **request body** (form-encoded or JSON) — never in the query string.

The response is `{ "access_token": ..., "expires_in": 3600, "token_type": "bearer" }`. Send it as
`Authorization: Bearer <access_token>` on every subsequent call and refresh it when `expires_in`
elapses. Do not use the relative `tokenUrl` from the OpenAPI — it does not resolve to a working
endpoint under the declared server. See `authentication/gofundme-authentication.yml`.

## 2. Find the campaign

- `listOrganizationCampaigns` — `GET /organizations/{organization}/campaigns`
- `fetchCampaign` — `GET /campaigns/{campaign}` for the single campaign, including its goal and
  totals.

Use `?with=organization,designation` to hydrate related resources in one call rather than
round-tripping.

## 3. Read the fundraising entities

- `listCampaignFundraisingPages` — `GET /campaigns/{campaign}/fundraising-pages`
- `listCampaignFundraisingTeams` — `GET /campaigns/{campaign}/fundraising-teams`

Rank them with the `sort` parameter (for example `sort=total_raised:desc`) rather than pulling every
page and sorting client-side. Narrow the payload with `fields` to just what the UI renders.

## 4. Get per-entity totals

- `fetchFundraisingPageOverview` — `GET /fundraising-pages/{fundraising_page}/overview`
- `fetchFundraisingTeamOverview` — `GET /fundraising-teams/{fundraising_team}/overview`

## Pagination

Every list operation is page-numbered: `page` (default 1) and `per_page` (default 20, **max 100**).
The response envelope carries `current_page`, `last_page`, `next_page_url`, `total` and `links[]`.
Walk `next_page_url` until it is null. There are no cursors.

## Rate limits

1,800 requests per minute per application. Watch `X-RateLimit-Remaining`; on a `429` read
`retry_after` from the body and the `Retry-After` header, and back off exponentially. Cache
leaderboard results — this is a read-heavy display flow and the docs explicitly recommend caching.

## Errors

Plain JSON, not RFC 9457. A `403` means the credential lacks permission (or the feature is not
enabled for the organization); a `404` names the missing resource in `error`. See
`errors/gofundme-problem-types.yml`.

## Reference implementations

- https://github.com/classy-org/custom-progress-bar-sample-app
- https://github.com/classy-org/custom-leaderboard-sample-app
