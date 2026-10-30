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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

GoFundMe is the world's largest social fundraising platform, operating both the consumer crowdfunding site at gofundme.com and GoFundMe Pro (formerly Classy, acquired in 2022) — the enterprise fundraising suite nonprofits use for donation pages, peer-to-peer campaigns, recurring giving, ticketed events and Giving Cart checkout. The developer surface is GoFundMe Pro: a REST API (v2.0) documented with a public OpenAPI 3.0 definition covering campaigns, transactions, supporters, fundraising pages and teams, recurring donation plans, designations, promo codes, payouts and reporting; OAuth2 client-credentials and member tokens; Svix-powered webhooks for supporter, transaction and recurring-plan events; a Classy Login OpenID Connect single-sign-on service; and Classy Pay embedded checkout. The consumer gofundme.com product publishes no public API.

**Areas:** Fundraising · Non-Profit · Crowdfunding · Donations · Payments · Peer-to-Peer Fundraising · Recurring Giving · Event · Philanthropy · Social Impact · CRM · Webhook

## GoFundMe on APIs.io

Everything profiled for GoFundMe is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/gofundme/](https://apis.io/providers/gofundme/)** — or go straight to one of the APIs or properties below.

### APIs (72)

- [Classy Login (OpenID Connect SSO)](https://apis.io/apis/gofundme/classy-login-openid-connect-sso/) — GoFundMe Pro's single sign-on service, implemented against OpenID Connect, letting third-party apps register and log people in with their Classy/GoFundMe…
- [Classy Pay](https://apis.io/apis/gofundme/classy-pay/) — Payment and embedded-checkout service behind GoFundMe Pro donation and registration flows. Ships a JavaScript embedded-checkout library (classypay.js) that…
- [GoFundMe Acknowledgement API](https://apis.io/apis/gofundme/gofundme-acknowledgement-api/) — An acknowledgement is a means of indicating that the member who made a transaction has been formally thanked. Every acknowledgement is made by the…
- [GoFundMe Activity API](https://apis.io/apis/gofundme/gofundme-activity-api/) — An activity is a record of an interaction with the GoFundMe Pro platform. Activity types include creating a new donation, creating a new fundraising page or…
- [GoFundMe Annual Summary API](https://apis.io/apis/gofundme/gofundme-annual-summary-api/) — Annual Summary
- [GoFundMe Answer API](https://apis.io/apis/gofundme/gofundme-answer-api/) — Answer objects represent an answer to a Question that is associated with an answerable_type (referenced by answerable_id and answerable_type), supported…
- [GoFundMe API App API](https://apis.io/apis/gofundme/gofundme-api-app-api/) — An App represents a client that can interact with GoFundMe Pro API.
- [GoFundMe Appeal Set API](https://apis.io/apis/gofundme/gofundme-appeal-set-api/) — An appeal set is a group of campaign specific appeals for social media. The current appeals that are supported include Facebook, Twitter, SMS, and Email.…
- [GoFundMe Branding API](https://apis.io/apis/gofundme/gofundme-branding-api/) — Organizations can have branding images and styles that will be applied to various areas of the GoFundMe Pro platform. Examples include changing the GoFundMe…
- [GoFundMe Brandkit API](https://apis.io/apis/gofundme/gofundme-brandkit-api/) — Brandkit
- [GoFundMe Campaign API](https://apis.io/apis/gofundme/gofundme-campaign-api/) — The fundraising aspect of GoFundMe Pro takes place within Campaigns and Events. Use the campaign endpoint to retrieve information about a campaign by its…
- [GoFundMe Campaign Channel API](https://apis.io/apis/gofundme/gofundme-campaign-channel-api/) — Campaign Channel is an Integration channel association available for specific Campaign. Integration channels will be like Facebook, Double the Donation.…
- [GoFundMe Campaign Credential Set API](https://apis.io/apis/gofundme/gofundme-campaign-credential-set-api/) — A Credential Set is fundamentally a record that dictates what a user can do or access within a Campaign or Organization context in the API.
- [GoFundMe Campaign Series API](https://apis.io/apis/gofundme/gofundme-campaign-series-api/) — A Campaign Series is a time series of campaigns.
- [GoFundMe Campaign Series Iteration API](https://apis.io/apis/gofundme/gofundme-campaign-series-iteration-api/) — A Campaign Series Iteration is one time span in a Campaign Series, e.g. '2024'
- [GoFundMe Campaign Studio API](https://apis.io/apis/gofundme/gofundme-campaign-studio-api/) — Campaign Studio
- [GoFundMe Channel Fundraising Entity API](https://apis.io/apis/gofundme/gofundme-channel-fundraising-entity-api/) — Channel Fundraising Entity will be used to store additional channel details for the fundraising entity. Where fundraising_entity_id is the ID of the…
- [GoFundMe Chariot API](https://apis.io/apis/gofundme/gofundme-chariot-api/) — Chariot
- [GoFundMe Classy Subscription Plan API](https://apis.io/apis/gofundme/gofundme-classy-subscription-plan-api/) — A ClassySubscriptionPlan is a legacy method of specifying the GoFundMe Pro plan to which an organization is subscribed, which was associated with specific…
- [GoFundMe Comment API](https://apis.io/apis/gofundme/gofundme-comment-api/) — Comments can also be made in response to Stories, Updates, or FeedItems made on a fundraising entity. Please note that these take a slightly different form…
- [GoFundMe Credit Adjustment API](https://apis.io/apis/gofundme/gofundme-credit-adjustment-api/) — A credit adjustment represents against a debit or credit fundraising entity's fundraising total (aka total_raised). This adjustment represents credit…
- [GoFundMe Dedication API](https://apis.io/apis/gofundme/gofundme-dedication-api/) — When a donation is dedicated to a specific individual, it can trigger a series of actions. An email message, crafted by the donor, is sent to the dedicatee.…
- [GoFundMe Designation API](https://apis.io/apis/gofundme/gofundme-designation-api/) — A Designation refers to a specific cause the organization campaigns under. Multiple campaigns can benefit the designated project. Designations allow me to…
- [GoFundMe Domain Slug API](https://apis.io/apis/gofundme/gofundme-domain-slug-api/) — A Domain Slug is a value used to shorten a URL by referencing a domain and a fundraising entity.
- [GoFundMe Donation Matching Plan API](https://apis.io/apis/gofundme/gofundme-donation-matching-plan-api/) — Donation matching occurs when a Sponsor - company or individual - agrees to match your campaign donations for a specific time period and/or up to a certain…
- [GoFundMe Double the Donation API](https://apis.io/apis/gofundme/gofundme-double-the-donation-api/) — The Double the Donation API from GoFundMe — 2 operation(s) for double the donation.
- [GoFundMe E Card API](https://apis.io/apis/gofundme/gofundme-ecard-api/) — Donors can send an eCard dedication along with their donation. Currently, a single campaign can support a maximum of 4 eCards. eCards are 600 pixels wide by…
- [GoFundMe Engagement Settings API](https://apis.io/apis/gofundme/gofundme-engagement-settings-api/) — Organization specific settings related to engagements such as email and SMS settings. We can set SMS numbers or email DNS, throttling etc.
- [GoFundMe FAQ API](https://apis.io/apis/gofundme/gofundme-faq-api/) — An FAQ (short for Frequently Asked Question) is a means of answering common questions that donors or registrants may have when donating/registering for a…
- [GoFundMe Feed Item API](https://apis.io/apis/gofundme/gofundme-feed-item-api/) — A feed item is a representation of a message that populates the feed of a fundraising entity (i.e. the feed item’s “feedable”). Each feed item references an…
- [GoFundMe Fundraising Page API](https://apis.io/apis/gofundme/gofundme-fundraising-page-api/) — A fundraising page is a means for an individual fundraiser to raise funds for a specific peer-to-peer campaign. Like other fundraising entities, each page…
- [GoFundMe Fundraising Page Transfer API](https://apis.io/apis/gofundme/gofundme-fundraising-page-transfer-api/) — Transfer Fundraising Page to another Member, Campaign or Fundraising Team.
- [GoFundMe Fundraising Team API](https://apis.io/apis/gofundme/gofundme-fundraising-team-api/) — Represents a group of donors consisting of a team lead fundraising together to reach a fundraising goal.
- [GoFundMe Fundraising Team Policy API](https://apis.io/apis/gofundme/gofundme-fundraising-team-policy-api/) — The Fundraising Team Policy represents a settings policy that can be applied to a Fundraising Team (parent, or sub-team). Fundraising Team Policy attributes…
- [GoFundMe Fundraising Team Transfer API](https://apis.io/apis/gofundme/gofundme-fundraising-team-transfer-api/) — Transfer a Fundraising Team within its Campaign/subteam infrastructure. This is done by specifying the team's direct parent, making it either a direct team…
- [GoFundMe GFM NPO Page API](https://apis.io/apis/gofundme/gofundme-gfm-npo-page-api/) — GFM NPO Page
- [GoFundMe Hard Credit Transfer API](https://apis.io/apis/gofundme/gofundme-hard-credit-transfer-api/) — A hard credit transfer is a means of transferring a hard credit (i.e. transaction) between fundraising entities associated with the same organization.
- [GoFundMe Like API](https://apis.io/apis/gofundme/gofundme-like-api/) — A like is a small show of approval for its associated 'likeable' entity. At the moment, the API allows Stories, Updates, FeedItems, and Comments to be…
- [GoFundMe Matched Transaction API](https://apis.io/apis/gofundme/gofundme-matched-transaction-api/) — A matched transaction can be created when a normal transaction may be matched with a future transaction. This might occur in the case of an employer match,…
- [GoFundMe Member API](https://apis.io/apis/gofundme/gofundme-member-api/) — A Member can be registered by directly having their attributes submitted (first_name, last_name, email_address, ...), or from their facebook account. To…
- [GoFundMe Organization API](https://apis.io/apis/gofundme/gofundme-organization-api/) — Represents an organization account. An organization's `currency_code` is used for Passport functionality. `currency_code` dictates the currency code that is…
- [GoFundMe Organization Channel API](https://apis.io/apis/gofundme/gofundme-organization-channel-api/) — An organization channel is a method of configuring an integration between an organization and a third-party event service (e.g. Facebook).
- [GoFundMe Organization Consumer Mappings API](https://apis.io/apis/gofundme/gofundme-organization-consumer-mappings-api/) — Organization Consumer Mappings
- [GoFundMe Organization Credential Set API](https://apis.io/apis/gofundme/gofundme-organization-credential-set-api/) — A Credential Set is fundamentally a record that dictates what a user can do or access within a Campaign or Organization context in the API.
- [GoFundMe Organization Notification API](https://apis.io/apis/gofundme/gofundme-organization-notification-api/) — The Organization Notification API from GoFundMe — 2 operation(s) for organization notification.
- [GoFundMe Organizations API](https://apis.io/apis/gofundme/gofundme-organizations-api/) — Organizations
- [GoFundMe Payouts API](https://apis.io/apis/gofundme/gofundme-payouts-api/) — Payouts will provide transactions of PayPal and Stripe.
- [GoFundMe Promo Code API](https://apis.io/apis/gofundme/gofundme-promo-code-api/) — A promo code record represents a shareable string that can be used to apply a discount to the purchase of one or more configured ticket types for a…
- [GoFundMe Promo Code Configuration API](https://apis.io/apis/gofundme/gofundme-promo-code-configuration-api/) — A promo code configuration record indicates that its associated promo code can be applied to purchases of the associated ticket type.
- [GoFundMe Question API](https://apis.io/apis/gofundme/gofundme-question-api/) — Questions are set up by organizations learn more about their supporters and fundraisers. These questions appear as a supporter signs up to fundraise or when…
- [GoFundMe Recurring Donation Plan API](https://apis.io/apis/gofundme/gofundme-recurring-donation-plan-api/) — A Recurring Donation Plan is a record of a user's intent to provide recurring donations towards a campaign or fundraising page. The record itself contains…
- [GoFundMe Recurring Donation Plan History API](https://apis.io/apis/gofundme/gofundme-recurring-donation-plan-history-api/) — A Recurring Donation Plan History is a history record of Recurring Donation Plan.
- [GoFundMe Registration API](https://apis.io/apis/gofundme/gofundme-registration-api/) — Registration records show information pertaining to event attendance, either through a ticket purchase or basic registration.
- [GoFundMe Reports API](https://apis.io/apis/gofundme/gofundme-reports-api/) — Reports
- [GoFundMe Restricted Country API](https://apis.io/apis/gofundme/gofundme-restricted-country-api/) — Restrict countries to have restricted usage of GoFundMe Pro such as for GDPR
- [GoFundMe Role API](https://apis.io/apis/gofundme/gofundme-role-api/) — Organizations and Campaigns have roles that can be assigned to Members.
- [GoFundMe Social Video API](https://apis.io/apis/gofundme/gofundme-social-video-api/) — Social Video
- [GoFundMe Soft Credit API](https://apis.io/apis/gofundme/gofundme-softcredit-api/) — Soft credits serve to allocate credit from part or all of the funds raised for a fundraising entity to any of its associated entities. For example, a…
- [GoFundMe Source Tracking Codes API](https://apis.io/apis/gofundme/gofundme-source-tracking-codes-api/) — Some Organizations have multiple marketing channels to support their cause. Source Tracking Codes are internal codes GoFundMe Pro uses to identify which…
- [GoFundMe Staff Notification Setting API](https://apis.io/apis/gofundme/gofundme-staff-notification-setting-api/) — Notification settings are for sending email notifications for different scopes as Organization and Campaign. Based on settings, email notification will be…
- [GoFundMe Story API](https://apis.io/apis/gofundme/gofundme-story-api/) — A type of post meant for display on a fundraising entity's page. This allows an administrator for the fundraising entity to present an appeal for donations…
- [GoFundMe Studio Campaign API](https://apis.io/apis/gofundme/gofundme-studio-campaign-api/) — Studio Campaign
- [GoFundMe Supporter API](https://apis.io/apis/gofundme/gofundme-supporter-api/) — A donor profile that’s owned by the organization. When an organization makes an update to a supporter, it will not affect member profile.
- [GoFundMe Supporters API](https://apis.io/apis/gofundme/gofundme-supporters-api/) — Supporters
- [GoFundMe Theme API](https://apis.io/apis/gofundme/gofundme-theme-api/) — It is a Campaign Theme which is used to set Theme properties like pages (landing, donation, thank you, etc) and styles for the Theme.
- [GoFundMe Ticket Type API](https://apis.io/apis/gofundme/gofundme-ticket-type-api/) — A Ticket Type defines the available ticket(s) for a ticketed Campaign. For example, ‘General Admission’ or ‘VIP’ * This defines what types of tickets are…
- [GoFundMe Transaction API](https://apis.io/apis/gofundme/gofundme-transaction-api/) — Transactions have three types of attributes relating to Passport: raw, charged, and normalized. Raw attributes reflect the donor/purchaser's intent when…
- [GoFundMe Transaction Item API](https://apis.io/apis/gofundme/gofundme-transaction-item-api/) — Transaction Items describe the specific donations, tickets, registrations (and more) that could make up a Transaction. Some transactions will only have a…
- [GoFundMe Transaction Receipt API](https://apis.io/apis/gofundme/gofundme-transaction-receipt-api/) — Transaction receipts record any instance when a specific transaction is produced for a donation.
- [GoFundMe Update API](https://apis.io/apis/gofundme/gofundme-update-api/) — A type of post meant for display on a fundraising entity's page. This allows and administrator for the fundraising entity to provide donors or registrants…
- [GoFundMe Whitelisted Currency API](https://apis.io/apis/gofundme/gofundme-whitelisted-currency-api/) — A record indicating one of the possible currencies that an organization is allowing for fundraising and transactions. If no such records exist for an…
- [GoFundMe Magic Link API](https://apis.io/apis/gofundme/gofundme-magic-link-api/) — MagicLink

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Gofundme Webhooks](https://apis.io/asyncapis/gofundme/gofundme-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [gofundme-pro](https://apis.io/servers/gofundme/gofundme-pro/)

#### Collections (70)

Postman and Open Collection request collections.

- [GoFundMe Pro Acknowledgement API](https://apis.io/collections/gofundme/open-gofundme-acknowledgement-api/)
- [GoFundMe Pro Activity API](https://apis.io/collections/gofundme/open-gofundme-activity-api/)
- [GoFundMe Pro Annual Summary API](https://apis.io/collections/gofundme/open-gofundme-annual-summary-api/)
- [GoFundMe Pro Answer API](https://apis.io/collections/gofundme/open-gofundme-answer-api/)
- [GoFundMe Pro API App API](https://apis.io/collections/gofundme/open-gofundme-api-app-api/)
- [GoFundMe Pro Appeal Set API](https://apis.io/collections/gofundme/open-gofundme-appeal-set-api/)
- [GoFundMe Pro Branding API](https://apis.io/collections/gofundme/open-gofundme-branding-api/)
- [GoFundMe Pro Brandkit API](https://apis.io/collections/gofundme/open-gofundme-brandkit-api/)
- [GoFundMe Pro Campaign API](https://apis.io/collections/gofundme/open-gofundme-campaign-api/)
- [GoFundMe Pro Campaign Channel API](https://apis.io/collections/gofundme/open-gofundme-campaign-channel-api/)
- [GoFundMe Pro Campaign Credential Set API](https://apis.io/collections/gofundme/open-gofundme-campaign-credential-set-api/)
- [GoFundMe Pro Campaign Series API](https://apis.io/collections/gofundme/open-gofundme-campaign-series-api/)
- [GoFundMe Pro Campaign Series Iteration API](https://apis.io/collections/gofundme/open-gofundme-campaign-series-iteration-api/)
- [GoFundMe Pro Campaign Studio API](https://apis.io/collections/gofundme/open-gofundme-campaign-studio-api/)
- [GoFundMe Pro Channel Fundraising Entity API](https://apis.io/collections/gofundme/open-gofundme-channel-fundraising-entity-api/)
- [GoFundMe Pro Chariot API](https://apis.io/collections/gofundme/open-gofundme-chariot-api/)
- [GoFundMe Pro Classy Subscription Plan API](https://apis.io/collections/gofundme/open-gofundme-classy-subscription-plan-api/)
- [GoFundMe Pro Comment API](https://apis.io/collections/gofundme/open-gofundme-comment-api/)
- [GoFundMe Pro Credit Adjustment API](https://apis.io/collections/gofundme/open-gofundme-credit-adjustment-api/)
- [GoFundMe Pro Dedication API](https://apis.io/collections/gofundme/open-gofundme-dedication-api/)
- [GoFundMe Pro Designation API](https://apis.io/collections/gofundme/open-gofundme-designation-api/)
- [GoFundMe Pro Domain Slug API](https://apis.io/collections/gofundme/open-gofundme-domain-slug-api/)
- [GoFundMe Pro Donation Matching Plan API](https://apis.io/collections/gofundme/open-gofundme-donation-matching-plan-api/)
- [GoFundMe Pro Double the Donation API](https://apis.io/collections/gofundme/open-gofundme-double-the-donation-api/)
- [GoFundMe Pro E Card API](https://apis.io/collections/gofundme/open-gofundme-ecard-api/)
- …and 45 more published on APIs.io

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Gofundme Pro Api Overlay](https://apis.io/overlays/gofundme/gofundme-pro-api-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Gofundme Authentication](https://apis.io/security/gofundme/gofundme-authentication/)
- [Gofundme Domain Security](https://apis.io/security/gofundme/gofundme-domain-security/)
- [Gofundme Trust Center](https://apis.io/security/gofundme/gofundme-trust-center/)
- [Gofundme Vulnerability Disclosure](https://apis.io/security/gofundme/gofundme-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Gofundme Scopes](https://apis.io/scopes/gofundme/gofundme-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Gofundme Plans Pricing](https://apis.io/plans/gofundme/gofundme-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Gofundme Rate Limits](https://apis.io/rate-limits/gofundme/gofundme-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.gofundme.com)
- [Documentation](https://developers.gofundme.com/pro/overview/get-started)
- [Getting started](https://developers.gofundme.com/pro/overview/get-started)
- [API reference](https://developers.gofundme.com/pro/docs)
- [Pricing](https://pro.gofundme.com/c/pricing/)
- [Sign up](https://developers.gofundme.com/pro/overview/request-access)
- [Support](https://prosupport.gofundme.com/hc/en-us)
- [Changelog](https://prosupport.gofundme.com/hc/en-us/articles/37726683210267-Release-notes)
- [Blog](https://pro.gofundme.com/c/blog/)
- [Security](https://www.gofundme.com/c/security)
- [Compliance](https://www.gofundme.com/c/security)
- [Terms of service](https://pro.gofundme.com/c/legal/terms/)
- [Privacy policy](https://pro.gofundme.com/c/legal/privacy-notice/)
- [GitHub](https://github.com/classy-org)
- [Status](https://status.classy.org)

## API Evangelist rating

**Kin Score 64.8** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 60.1 |
| Contract governance | 4.5 |
| Operational transparency | 73.7 |
| Developer ergonomics | 47.0 |
| Access clarity | 75.0 |

**Agent readiness 43.0** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | verified |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 48.2** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/gofundme/](https://apis.io/providers/gofundme/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for GoFundMe: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/gofundme/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
