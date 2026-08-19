---
name: keap-sales-pipeline-management
description: >-
  Run a sales pipeline in Keap — create opportunities against contacts and companies,
  move them through stages, read the stage-move history for forecasting, and hang
  tasks and notes off the deal.
api: Keap REST v2
version: v2
base_url: https://api.infusionsoft.com/crm/rest/v2
generated: '2026-08-13'
method: generated
source: openapi/_original/keap-v2-openapi.json
operations:
  - createOpportunity
  - getOpportunity
  - updateOpportunity
  - deleteOpportunity
  - listOpportunityStages
  - createOpportunityStage
  - listOpportunityStageMoves
  - getOpportunityStageMove
  - retrieveOpportunityCustomFieldModel
  - listCompanies
  - createCompany
  - createTask
  - listTasks
  - updateTask
  - createNote
---

# Manage a sales pipeline in Keap

All operationIds are verified against Keap's published v2 OpenAPI. Do not invent
operations.

## 1. Know the stages before you write

`listOpportunityStages` — `GET /rest/v2/opportunities/stages`

Stages are account-configured data, not an enum in the spec. Always read them and match
by name or id; never hardcode a stage id across accounts. `createOpportunityStage`
exists if you are provisioning a new account, but treat it as an admin operation.

## 2. Establish the parties

- Contact: see `keap-lead-capture-and-tagging`. Dedupe before creating.
- Company: `listCompanies` — `GET /rest/v2/companies` — then `createCompany` only if
  absent. Companies carry their own tags (`addTagToCompany` /
  `removeTagFromCompany`) and their own custom-field model.

## 3. Create the opportunity

`createOpportunity` — `POST /rest/v2/opportunities`

Before writing custom fields, call `retrieveOpportunityCustomFieldModel` —
`GET /rest/v2/opportunities/model` — to discover what the account has configured.

**No idempotency key exists.** If the call times out, run
`GET /rest/v2/opportunities` with a `filter` before retrying, or you will create a
second deal.

## 4. Move it through the pipeline

`updateOpportunity` — `PATCH /rest/v2/opportunities/{opportunity_id}`

This is a field-mask patch: pass `update_mask` as a query parameter naming exactly the
fields you are changing — typically the stage — and everything else is left alone. A
PATCH without `update_mask` will not behave like a merge patch.

## 5. Read the history for forecasting

`listOpportunityStageMoves` — `GET /rest/v2/opportunities/stageMoves`
`getOpportunityStageMove` — `GET /rest/v2/opportunities/stageMoves/{stage_move_id}`

This is the artifact most integrations miss. Stage moves are first-class records, so
velocity, stage dwell time and conversion rates come from the API rather than from
diffing snapshots. Paginate with `page_size`/`page_token` and sort with `order_by`.

## 6. Attach follow-up

- `createTask` — `POST /rest/v2/tasks` — the next action. `listTasks` and `updateTask`
  to work the queue.
- `createNote` — `POST /rest/v2/contacts/{contact_id}/notes` — notes are
  **contact-scoped** in v2, not opportunity-scoped. Record the opportunity id in the
  note body if you need the link.

## Errors and limits

- Uniform declared error set: 400, 401, 403, 404, 405, 409, 500, 501 with
  `{code, message, status, details[]}` as `application/json`.
- 429 is undeclared in the spec but enforced. Read `x-keap-tenant-throttle-available`
  and `x-keap-product-quota-available` on every response.
- Pagination is cursor-based (`page_size`, `page_token`, `next_page_token`) — do not
  assume offsets; that is the v1 style.

## References

- Data model: `data-model/keap-data-model.yml`
- Conventions: `conventions/keap-conventions.yml`
- Spec: `openapi/keap-opportunity-api-openapi.yml`, `openapi/keap-company-api-openapi.yml`
