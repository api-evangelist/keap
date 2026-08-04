# Keap (keap)

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

Keap (formerly Infusionsoft) is a customer relationship management (CRM), sales, and marketing automation platform for small businesses that combines contact management, email marketing, e-commerce, and pipeline automation. The Keap REST API provides programmatic access to contacts, companies, opportunities, orders, products, tasks, campaigns, and tags using OAuth 2.0 or Personal Access Tokens.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/keap/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/keap/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- CRM
- Sales
- Marketing Automation
- Small Business
- E-Commerce
- Contacts

## Timestamps

- **Created:** 2026-05-11
- **Modified:** 2026-05-30

## APIs

### Keap REST API

REST API for managing contacts, companies, opportunities, orders, products, tasks, campaigns, tags, and emails in Keap CRM. Authentication uses OAuth 2.0, Personal Access Tokens, or Service Account API Keys.

- **Human URL:** [https://developer.infusionsoft.com/docs/restv2/](https://developer.infusionsoft.com/docs/restv2/)
- **Base URL:** `https://api.infusionsoft.com/crm/rest/v2`

#### Tags

- CRM
- Contacts
- Sales
- Marketing Automation
- Orders
- Campaigns

#### Properties

- [Documentation](https://developer.infusionsoft.com/docs/restv2/)
- [A P I  Reference v1](https://developer.infusionsoft.com/docs/rest/)
- [Authentication](https://developer.infusionsoft.com/authentication/)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/keap/refs/heads/main/openapi/keap-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/keap.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/keap.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Keap REST Hooks

Keap REST Hooks webhook surface. Subscribers register a `hookUrl` and `eventKey` via the v1 REST API (`POST /rest/v1/hooks`), complete an `X-Hook-Secret` verification handshake, then receive HTTP POST deliveries when contact, contactGroup, opportunity, invoice, order, and subscription events occur. Event types follow `noun.verb` dot-syntax (for example `contact.add`, `invoice.delete`).

- **Human URL:** [https://developer.infusionsoft.com/rest-hook-documentation/](https://developer.infusionsoft.com/rest-hook-documentation/)
- **Base URL:** `https://api.infusionsoft.com/crm/rest/v1/hooks`

#### Tags

- Webhooks
- REST Hooks
- Events
- CRM
- Contacts
- Opportunities
- Invoices
- Orders
- Subscriptions

#### Properties

- [Documentation](https://developer.infusionsoft.com/rest-hook-documentation/)
- [A P I  Reference](https://developer.infusionsoft.com/docs/rest/)
- [AsyncAPI](https://raw.githubusercontent.com/api-evangelist/keap/refs/heads/main/asyncapi/keap-resthooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/keap.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/keap.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/keap-growing)
- [Website](https://keap.com)
- [Documentation](https://developer.infusionsoft.com/)
- [Sign Up](https://keap.com/signup)
- [Pricing](https://keap.com/pricing)
- [Developer  Portal](https://developer.infusionsoft.com/)
- [O Auth](https://developer.infusionsoft.com/getting-started-oauth-keys/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
