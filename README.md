# Keap

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

Keap (formerly Infusionsoft, now part of Thryv) is a CRM, sales and marketing automation platform for small businesses that combines contact management, email and text marketing, e-commerce, affiliate management and pipeline automation. Keap publishes two live OpenAPI 3.1 contracts covering 540 operations — REST v2 (399 operations, the Default version) and REST v1 (141 operations, still the only home of REST Hooks webhooks and Appointments) — plus a deprecated XML-RPC surface. Authentication is OAuth 2.0 authorization code with rotating refresh tokens, or Personal Access Tokens and Service Account Keys, all with a single `full` scope. Keap also operates an undocumented but live remote MCP server at https://api.keap.com/mcp secured with OAuth 2.1, PKCE and dynamic client registration, and ships first-party SDKs for six languages generated in lock-step from its own spec.

**Areas:** CRM · Sales · Marketing Automation · Small Business · E-Commerce · Contacts · Email Marketing · Subscription · Affiliate Management · Webhook · MCP · Payments

## Keap on APIs.io

Everything profiled for Keap is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/keap/](https://apis.io/providers/keap/)** — or go straight to one of the APIs or properties below.

### APIs (59)

- [Keap Affiliate API](https://apis.io/apis/keap/keap-affiliate-api/) — Keap Affiliate API — 48 operations across 28 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Automation API](https://apis.io/apis/keap/keap-automation-api/) — Keap Automation API — 10 operations across 9 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Campaigns API](https://apis.io/apis/keap/keap-campaigns-api/) — Keap Campaign API — 6 operations across 6 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Category Discounts API](https://apis.io/apis/keap/keap-category-discounts-api/) — Keap Category Discounts API — 7 operations across 4 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Companies API](https://apis.io/apis/keap/keap-companies-api/) — Keap Company API — 22 operations across 11 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Contacts API](https://apis.io/apis/keap/keap-contacts-api/) — Keap Contact API — 27 operations across 16 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Email API](https://apis.io/apis/keap/keap-email-api/) — Keap Email API — 10 operations across 8 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Files API](https://apis.io/apis/keap/keap-files-api/) — Keap Files API — 6 operations across 3 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Free Trial Discounts API](https://apis.io/apis/keap/keap-free-trial-discounts-api/) — Keap Free Trial Discounts API — 7 operations across 4 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Lead Source Categories API](https://apis.io/apis/keap/keap-lead-source-categories-api/) — Keap Lead Source Categories API — 5 operations across 2 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Lead Source Expenses API](https://apis.io/apis/keap/keap-lead-source-expenses-api/) — Keap Lead Source Expenses API — 5 operations across 2 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Lead Source Recurring Expenses API](https://apis.io/apis/keap/keap-lead-source-recurring-expenses-api/) — Keap Lead Source Recurring Expenses API — 6 operations across 3 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Lead Sources API](https://apis.io/apis/keap/keap-lead-sources-api/) — Keap Lead Sources API — 5 operations across 2 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Note API](https://apis.io/apis/keap/keap-note-api/) — Keap Note API — 21 operations across 11 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Opportunities API](https://apis.io/apis/keap/keap-opportunities-api/) — Keap Opportunity API — 26 operations across 13 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Order Total Discounts API](https://apis.io/apis/keap/keap-order-total-discounts-api/) — Keap Order Total Discounts API — 7 operations across 4 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Orders API](https://apis.io/apis/keap/keap-orders-api/) — Keap Orders API — 29 operations across 16 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Product Categories API](https://apis.io/apis/keap/keap-product-categories-api/) — Keap Product Categories API — 9 operations across 5 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Product Discounts API](https://apis.io/apis/keap/keap-product-discounts-api/) — Keap Product Discounts API — 7 operations across 4 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Product Interest Bundles API](https://apis.io/apis/keap/keap-product-interest-bundles-api/) — Keap Product Interest Bundles API — 8 operations across 4 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Products API](https://apis.io/apis/keap/keap-products-api/) — Keap Products API — 17 operations across 9 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Shipping Discounts API](https://apis.io/apis/keap/keap-shipping-discounts-api/) — Keap Shipping Discounts API — 7 operations across 4 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Subscription Plans API](https://apis.io/apis/keap/keap-subscription-plans-api/) — Keap Subscription Plans API — 5 operations across 2 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Subscriptions API](https://apis.io/apis/keap/keap-subscriptions-api/) — Keap Subscriptions API — 20 operations across 11 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Tags API](https://apis.io/apis/keap/keap-tags-api/) — Keap Tags API — 14 operations across 8 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Tasks API](https://apis.io/apis/keap/keap-tasks-api/) — Keap Task API — 19 operations across 9 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Users API](https://apis.io/apis/keap/keap-users-api/) — Keap Users API — 5 operations across 4 paths on the Keap REST v2 contract, read from Keap's own published OpenAPI 3.1 document.
- [Keap Appointment API](https://apis.io/apis/keap/keap-appointment-api/) — The Appointment API from Keap — 4 operation(s) for appointment.
- [Keap File API](https://apis.io/apis/keap/keap-file-api/) — The File API from Keap — 2 operation(s) for file.
- [Keap Product API](https://apis.io/apis/keap/keap-product-api/) — The Product API from Keap — 6 operation(s) for product.
- [Keap REST Hooks API](https://apis.io/apis/keap/keap-rest-hooks-api/) — The REST Hooks API from Keap — 5 operation(s) for rest hooks.
- [Keap Account Info API](https://apis.io/apis/keap/keap-account-info-api/) — Account Info-Endpoint
- [Keap Automation Category API](https://apis.io/apis/keap/keap-automationcategory-api/) — The AutomationCategory API from Keap — 2 operation(s) for automationcategory.
- [Keap Business Profile API](https://apis.io/apis/keap/keap-business-profile-api/) — The Business Profile API from Keap — 1 operation(s) for business profile.
- [Keap Email Address API](https://apis.io/apis/keap/keap-email-address-api/) — Email-Addresses-Endpoint
- [Keap Integrations API](https://apis.io/apis/keap/keap-integrations-api/) — The Integrations API from Keap — 3 operation(s) for integrations.
- [Keap Lead Score API](https://apis.io/apis/keap/keap-leadscore-api/) — The LeadScore API from Keap — 1 operation(s) for leadscore.
- [Keap Locale API](https://apis.io/apis/keap/keap-locale-api/) — Locale-Endpoint
- [Keap Merchant API](https://apis.io/apis/keap/keap-merchant-api/) — Merchant-Endpoint
- [Keap Merchants API](https://apis.io/apis/keap/keap-merchants-api/) — The Merchants API from Keap — 1 operation(s) for merchants.
- [Keap Payment Method Configs API](https://apis.io/apis/keap/keap-payment-method-configs-api/) — The Payment Method Configs API from Keap — 1 operation(s) for payment method configs.
- [Keap Payment Methods API](https://apis.io/apis/keap/keap-payment-methods-api/) — The Payment Methods API from Keap — 4 operation(s) for payment methods.
- [Keap Referral API](https://apis.io/apis/keap/keap-referral-api/) — The Referral API from Keap — 1 operation(s) for referral.
- [Keap Reporting API](https://apis.io/apis/keap/keap-reporting-api/) — The Reporting API from Keap — 4 operation(s) for reporting.
- [Keap Sales API](https://apis.io/apis/keap/keap-sales-api/) — The Sales API from Keap — 3 operation(s) for sales.
- [Keap Setting API](https://apis.io/apis/keap/keap-setting-api/) — Setting-Endpoint
- [Keap Settings API](https://apis.io/apis/keap/keap-settings-api/) — The Settings API from Keap — 3 operation(s) for settings.
- [Keap Shipping API](https://apis.io/apis/keap/keap-shipping-api/) — The Shipping API from Keap — 1 operation(s) for shipping.
- [Keap User Groups API](https://apis.io/apis/keap/keap-user-groups-api/) — The User Groups API from Keap — 2 operation(s) for user groups.
- [Keap Webforms API](https://apis.io/apis/keap/keap-webforms-api/) — The Webforms API from Keap — 2 operation(s) for webforms.
- [Keap XML-RPC API (legacy Infusionsoft)](https://apis.io/apis/keap/keap-xml-rpc-api/) — The legacy Infusionsoft XML-RPC API, explicitly labelled Deprecated in the Keap developer guide. It remains documented, with a published table schema…
- [Keap User Info API](https://apis.io/apis/keap/keap-user-info-api/) — UserInfo-Endpoint
- [Keap Custom Fields API](https://apis.io/apis/keap/keap-custom-fields-api/) — The Custom Fields API from Keap — 2 operation(s) for custom fields.
- [Keap Date Expression API](https://apis.io/apis/keap/keap-dateexpression-api/) — The DateExpression API from Keap — 1 operation(s) for dateexpression.
- [Keap Deals API](https://apis.io/apis/keap/keap-deals-api/) — The Deals API from Keap — 12 operation(s) for deals.
- [Keap Display Forms API](https://apis.io/apis/keap/keap-display-forms-api/) — The Display Forms API from Keap — 1 operation(s) for display forms.
- [Keap Pipelines API](https://apis.io/apis/keap/keap-pipelines-api/) — The Pipelines API from Keap — 8 operation(s) for pipelines.
- [Keap Stages API](https://apis.io/apis/keap/keap-stages-api/) — The Stages API from Keap — 4 operation(s) for stages.
- [Keap Ecommerce API](https://apis.io/apis/keap/keap-ecommerce-api/) — E-Commerce-Endpoint

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Keap REST Hooks](https://apis.io/asyncapis/keap/keap-resthooks-asyncapi/)

#### Event channels (15)

Individual events and webhooks the provider emits.

- [contact.add](https://apis.io/channels/keap/contact-add/)
- [contact.delete](https://apis.io/channels/keap/contact-delete/)
- [contact.edit](https://apis.io/channels/keap/contact-edit/)
- [contactGroup.applied](https://apis.io/channels/keap/contactgroup-applied/)
- [contactGroup.removed](https://apis.io/channels/keap/contactgroup-removed/)
- [hook.verification](https://apis.io/channels/keap/hook-verification/)
- [invoice.add](https://apis.io/channels/keap/invoice-add/)
- [invoice.edit](https://apis.io/channels/keap/invoice-edit/)
- [opportunity.add](https://apis.io/channels/keap/opportunity-add/)
- [opportunity.delete](https://apis.io/channels/keap/opportunity-delete/)
- [opportunity.edit](https://apis.io/channels/keap/opportunity-edit/)
- [order.add](https://apis.io/channels/keap/order-add/)
- [subscription.add](https://apis.io/channels/keap/subscription-add/)
- [subscription.delete](https://apis.io/channels/keap/subscription-delete/)
- [subscription.edit](https://apis.io/channels/keap/subscription-edit/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Keap MCP Server](https://apis.io/servers/keap/keap-mcp-server/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Keap Agentic Access](https://apis.io/agentic-access/keap/keap-agentic-access/)

#### Collections (9)

Postman and Open Collection request collections.

- [Keap REST API](https://apis.io/collections/keap/open-keap/)
- [Keap REST Campaigns API](https://apis.io/collections/keap/open-keap-campaigns-api/)
- [Keap REST Campaigns Companies API](https://apis.io/collections/keap/open-keap-companies-api/)
- [Keap REST Campaigns Contacts API](https://apis.io/collections/keap/open-keap-contacts-api/)
- [Keap REST Campaigns Opportunities API](https://apis.io/collections/keap/open-keap-opportunities-api/)
- [Keap REST Campaigns Orders API](https://apis.io/collections/keap/open-keap-orders-api/)
- [Keap REST Campaigns Products API](https://apis.io/collections/keap/open-keap-products-api/)
- [Keap REST Campaigns Tags API](https://apis.io/collections/keap/open-keap-tags-api/)
- [Keap REST Campaigns Tasks API](https://apis.io/collections/keap/open-keap-tasks-api/)

#### Overlays (32)

OpenAPI overlays, including conversational phrasing for each operation.

- [Keap Affiliate Overlay](https://apis.io/overlays/keap/keap-affiliate-overlay/)
- [Keap Appointment V1 Overlay](https://apis.io/overlays/keap/keap-appointment-v1-overlay/)
- [Keap Automation Overlay](https://apis.io/overlays/keap/keap-automation-overlay/)
- [Keap Campaign Overlay](https://apis.io/overlays/keap/keap-campaign-overlay/)
- [Keap Category Discounts Overlay](https://apis.io/overlays/keap/keap-category-discounts-overlay/)
- [Keap Company Overlay](https://apis.io/overlays/keap/keap-company-overlay/)
- [Keap Contact Overlay](https://apis.io/overlays/keap/keap-contact-overlay/)
- [Keap E Commerce V1 Overlay](https://apis.io/overlays/keap/keap-e-commerce-v1-overlay/)
- [Keap Email Overlay](https://apis.io/overlays/keap/keap-email-overlay/)
- [Keap File V1 Overlay](https://apis.io/overlays/keap/keap-file-v1-overlay/)
- [Keap Files Overlay](https://apis.io/overlays/keap/keap-files-overlay/)
- [Keap Free Trial Discounts Overlay](https://apis.io/overlays/keap/keap-free-trial-discounts-overlay/)
- [Keap Lead Source Categories Overlay](https://apis.io/overlays/keap/keap-lead-source-categories-overlay/)
- [Keap Lead Source Expenses Overlay](https://apis.io/overlays/keap/keap-lead-source-expenses-overlay/)
- [Keap Lead Source Recurring Expenses Overlay](https://apis.io/overlays/keap/keap-lead-source-recurring-expenses-overlay/)
- [Keap Lead Sources Overlay](https://apis.io/overlays/keap/keap-lead-sources-overlay/)
- [Keap Note Overlay](https://apis.io/overlays/keap/keap-note-overlay/)
- [Keap Opportunity Overlay](https://apis.io/overlays/keap/keap-opportunity-overlay/)
- [Keap Order Total Discounts Overlay](https://apis.io/overlays/keap/keap-order-total-discounts-overlay/)
- [Keap Orders Overlay](https://apis.io/overlays/keap/keap-orders-overlay/)
- [Keap Product Categories Overlay](https://apis.io/overlays/keap/keap-product-categories-overlay/)
- [Keap Product Discounts Overlay](https://apis.io/overlays/keap/keap-product-discounts-overlay/)
- [Keap Product Interest Bundles Overlay](https://apis.io/overlays/keap/keap-product-interest-bundles-overlay/)
- [Keap Product V1 Overlay](https://apis.io/overlays/keap/keap-product-v1-overlay/)
- [Keap Products Overlay](https://apis.io/overlays/keap/keap-products-overlay/)
- …and 7 more published on APIs.io

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Keap — asyncapi rules](https://apis.io/rules/keap/keap-asyncapi-spectral-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Keap Authentication](https://apis.io/security/keap/keap-authentication/)
- [Keap Domain Security](https://apis.io/security/keap/keap-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Keap Scopes](https://apis.io/scopes/keap/keap-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Keap Plans Pricing](https://apis.io/plans/keap/keap-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Keap Rate Limits](https://apis.io/rate-limits/keap/keap-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://keap.com)
- [Documentation](https://developer.infusionsoft.com/)
- [Getting started](https://developer.infusionsoft.com/getting-started-oauth-keys/)
- [API reference](https://developer.infusionsoft.com/docs/restv2/)
- [Pricing](https://keap.com/pricing)
- [Sign up](https://keys.developer.keap.com/accounts/create)
- [Support](https://developer.infusionsoft.com/get-support/)
- [Blog](https://keap.com/small-business-automation-blog)
- [Terms of service](https://www.thryv.com/terms/)
- [Privacy policy](https://www.thryv.com/privacy/)
- [GitHub](https://github.com/infusionsoft)
- [Status](https://status.thryv.com/)

## API Evangelist rating

**Kin Score 64.4** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.3 |
| Contract quality | 61.4 |
| Contract governance | 15.9 |
| Operational transparency | 34.2 |
| Developer ergonomics | 78.0 |
| Access clarity | 73.7 |

**Agent readiness 45.4** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | verified |
| MCP Server | verified |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | — |

**Regulatory alignment 35.7** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/keap/](https://apis.io/providers/keap/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Keap: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/keap/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
