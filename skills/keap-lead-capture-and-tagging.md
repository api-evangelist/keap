---
name: keap-lead-capture-and-tagging
description: >-
  Capture a new lead into Keap as a Contact, de-duplicate it against existing
  records, apply the tags that drive downstream automation, and attach a note
  recording where the lead came from. This is the single most common Keap
  integration flow.
api: Keap REST v2
version: v2
base_url: https://api.infusionsoft.com/crm/rest/v2
generated: '2026-08-13'
method: generated
source: openapi/_original/keap-v2-openapi.json
operations:
  - listContacts
  - createContact
  - updateContact
  - retrieveContactModel
  - listTags
  - createTag
  - applyTags
  - listTagsForContact
  - createNote
  - mergeContacts
---

# Capture a lead and tag it in Keap

All operationIds below are verified against Keap's published v2 OpenAPI
(`https://crm.infusionsoft.com/app/v3/api-docs/V2`). Do not invent operations.

## Before you start

- Authenticate with `Authorization: Bearer <token>` — an OAuth2 access token, a
  Personal Access Token, or a Service Account Key. There is exactly one OAuth scope:
  `full`.
- A Personal Access Token acts **as the user who created it** and inherits that user's
  visibility and edit permissions. A Service Account Key has admin access to everything.
- **There is no idempotency key on any Keap operation.** If a `createContact` call
  times out or you retry after a 429, you can create a duplicate. Always run step 1
  before step 2, and prefer `updateContact` over a second `createContact`.

## 1. Look for an existing contact first

`listContacts` — `GET /rest/v2/contacts`

Use the `filter` query parameter. Email is the reliable dedupe key:

```
GET /rest/v2/contacts?filter=email==jane@example.com&page_size=10
```

The `filter` language supports `==` with a trailing wildcard (`email==jane*`), and
`>`/`<`/`>=`/`<=` on numeric fields such as `contact_id` (URL-encode the operator).
You can also filter on `given_name`, `family_name`, `company_id`, `phone_number`
(requires `phone_fields`), the billing/shipping/other address fields, `city`, `state`,
`website` and `lead_source_name`.

Paginate with `page_size` + `page_token`; the response carries `next_page_token`.

## 2. Create or update

- No match → `createContact` — `POST /rest/v2/contacts`
- Match → `updateContact` — `PATCH /rest/v2/contacts/{contact_id}`

`updateContact` is a **field-mask** patch. Pass `update_mask` as a query parameter
listing exactly the fields you are changing; anything not named is left untouched.
There is no JSON Merge Patch or JSON Patch support.

If you discover two records for the same person, `mergeContacts`
(`POST /rest/v2/contacts:merge`) is the supported repair — it is destructive, so
confirm before calling.

### Custom fields

Call `retrieveContactModel` — `GET /rest/v2/contacts/model` — to discover the custom
fields configured on the account before writing to them. Custom fields are also
filterable in step 1 by their `field_name` (case-insensitive), except where a standard
field of the same name takes precedence.

## 3. Apply tags

Tags are what actually trigger Keap campaigns, so this step is where the automation
starts.

1. `listTags` — `GET /rest/v2/tags` — find the tag id. Filter and paginate the same way.
2. If it does not exist, `createTag` — `POST /rest/v2/tags` (optionally inside a
   category from `listTagCategories`).
3. `applyTags` — `POST /rest/v2/tags/{tag_id}/contacts:applyTags` — note the tag id is
   in the **path** and the contact ids are in the body. This is a batch operation.
4. Verify with `listTagsForContact` — `GET /rest/v2/contacts/{contact_id}/tags`.

To undo, `removeTags` — `POST /rest/v2/tags/{tag_id}/contacts:removeTags`.

## 4. Record provenance

`createNote` — `POST /rest/v2/contacts/{contact_id}/notes` — write where the lead came
from. Notes are contact-scoped in v2.

## Errors and limits

- Every operation declares 400, 401, 403, 404, 405, 409, 500 and 501 with the envelope
  `{code, message, status, details[]}` as `application/json`. This is **not** RFC 9457
  problem+json.
- **429 is not declared in the spec but will happen.** Limits: 1,500/min and
  150,000/day per OAuth key pair; 10/sec, 240/min and 30,000/day per PAT/SAK; 10,000/min
  and 250,000/day per application instance. Read `x-keap-product-quota-available` and
  `x-keap-tenant-throttle-available` on every response and back off exponentially.
- A 401 may arrive in a *different* envelope — the Apigee gateway returns
  `{"fault":{"faultstring":"Invalid access token",...}}` before the API is reached.
  Handle both shapes.
- Refresh tokens rotate: every refresh returns a new refresh token that must be
  persisted or the chain breaks.

## References

- Conventions: `conventions/keap-conventions.yml`
- Errors: `errors/keap-problem-types.yml`
- Rate limits: `rate-limits/keap-rate-limits.yml`
- Spec: `openapi/keap-contact-api-openapi.yml`, `openapi/keap-tags-api-openapi.yml`
