# Keap (keap)

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
