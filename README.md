# GoFundMe

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

GoFundMe is the world's largest social fundraising platform. It operates the consumer crowdfunding
site at gofundme.com and **GoFundMe Pro** (formerly Classy, acquired in 2022) — the enterprise
fundraising suite nonprofits use for donation pages, peer-to-peer campaigns, recurring giving,
ticketed events and Giving Cart checkout.

The developer surface is GoFundMe Pro. The consumer gofundme.com product publishes no public API.

## What GoFundMe Pro publishes

| Surface | Where |
| --- | --- |
| OpenAPI 3.0.0 — 201 paths, **290 operations**, 356 schemas, 70 tags | https://docs.classy.org/specs/apiv2-public.json |
| API reference (Redoc) | https://developers.gofundme.com/pro/docs |
| Developer portal | https://developers.gofundme.com/pro/overview/welcome |
| Base URL | `https://pro.gofundme.com/api/2.0` (also live at `https://api.classy.org/2.0`) |
| Auth | OAuth 2.0 — `POST https://api.classy.org/oauth2/auth`, client_credentials + authorization_code |
| Webhooks | Svix-delivered; 6 events across supporters, transactions, recurring plans |
| SSO | Classy Login (OpenID Connect, pre-release) |
| Checkout | Classy Pay embedded checkout (`classypay.js`) + staging environment |
| Status | https://status.classy.org |
| Release notes | https://prosupport.gofundme.com/hc/en-us/articles/37726683210267-Release-notes |
| SDKs | npm `classy-node`, Packagist `classy-org/classy-php-sdk`, WordPress plugin |
| Postman | https://github.com/classy-org/postman-collections |
| Security | https://www.gofundme.com/c/security — PCI DSS Level 1, private Bugcrowd bounty |

## Artifacts in this repository

- `openapi/` — the verbatim harvested OpenAPI 3.0.0 (and a copy under `_original/`)
- `authentication/`, `scopes/` — OAuth model, grants, token endpoint, the two coarse scopes
- `conventions/` — pagination, filtering, expansion, sorting, dates, idempotency, error envelope
- `errors/` — the derived problem-type catalog across 650 declared 4xx/5xx responses
- `rate-limits/` — 1,800 requests/minute per application and the `X-RateLimit-*` signalling
- `lifecycle/` — versioning, the deprecation schedule, status page, 54 deprecated operations
- `changelog/` — structured recent release notes
- `asyncapi/` — the webhook catalog (no AsyncAPI document is published)
- `data-model/` — the entity graph derived from 118 nested collection paths
- `conformance/`, `security/` — standards posture, domain security probes, disclosure, trust posture
- `packages/`, `components/`, `sandbox/` — SDKs, embeds, and what passes for a test environment
- `skills/` — four generated Agent Skills grounded in verified operationIds
- `mcp/` — a candidate tool surface derived from the spec (GoFundMe Pro ships no MCP server)
- `llms/`, `overlays/`, `well-known/` — agent-facing summary, our annotations, discovery probes

## Notable gaps found

- The OpenAPI's `tokenUrl` is relative and does not resolve to a working endpoint under the declared
  server — generated clients will fail until the absolute token URL is supplied.
- 251 of 290 operation summaries are the `operationId` repeated verbatim.
- The published deprecation schedule stops in 2016, yet 54 operations are flagged `deprecated`.
- No sandbox tenant or test credentials — every write is a production write.
- No AsyncAPI for the webhook surface, and no OIDC discovery document for Classy Login.
- First-party SDKs (npm 2019, Packagist 1.2.0) are years stale against a 290-operation API.
- No MCP server, no agent card, no llms.txt, no `/.well-known/` catalog.
- security.txt is published at `/security.txt` rather than the RFC 9116 canonical path, and its
  `Expires` value lapsed on 2026-01-01.
