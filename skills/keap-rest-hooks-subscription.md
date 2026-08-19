---
name: keap-rest-hooks-subscription
description: >-
  Subscribe to Keap change events instead of polling. Discover the available event
  keys, register a REST Hook, complete the X-Hook-Secret verification handshake,
  handle batched deliveries, and recover a subscription that Keap has deactivated.
api: Keap REST v1
version: v1
base_url: https://api.infusionsoft.com/crm/rest/v1
generated: '2026-08-13'
method: generated
source: >-
  openapi/_original/keap-v1-openapi.json +
  https://developer.infusionsoft.com/rest-hook-documentation/
operations:
  - list_hook_event_types
  - create_a_hook_subscription
  - verify_a_hook_subscription
  - verify_a_hook_subscription_delayed
  - list_stored_hook_subscriptions
  - retrieve_a_hook_subscription
  - update_a_hook_subscription
  - delete_a_hook_subscription
---

# Subscribe to Keap events with REST Hooks

**Webhooks live on v1 only.** The v2 contract has no hook endpoints. If you have
otherwise migrated to v2, you still call v1 for events. All operationIds are verified
against Keap's published v1 OpenAPI.

## 1. Discover the event keys

`list_hook_event_types` — `GET /rest/v1/hooks/event_keys`

This is the authoritative list; do not hardcode event names from documentation. Keys
use `noun.verb` dot syntax — for example `contact.add`, `contact.edit`,
`contactGroup.applied`, `invoice.delete`, `order.add`, `subscription.add`.

## 2. Register the subscription

`create_a_hook_subscription` — `POST /rest/v1/hooks`

Body carries your `hookUrl` and the `eventKey` you are subscribing to. One subscription
per event key.

## 3. Complete the verification handshake

A subscription delivers nothing until it is **Verified**. Two flows:

**Immediate confirmation.** On creation, Keap POSTs to your `hookUrl` carrying a
temporary `X-Hook-Secret` header. Respond `200` and **echo the same `X-Hook-Secret`
header and value back**. That is the whole handshake.

**Delayed confirmation.** If your receiver cannot echo synchronously, capture the
secret and later call `verify_a_hook_subscription_delayed` —
`POST /rest/v1/hooks/{key}/delayedVerify` — sending the `X-Hook-Secret` you received
back to Keap as a header.

Use `retrieve_a_hook_subscription` — `GET /rest/v1/hooks/{key}` — to confirm status.

## 4. Handle deliveries

Payload shape (from Keap's documentation):

```json
{
  "event_key": "contact.edit",
  "object_type": "contact",
  "object_keys": [
    { "id": 123, "apiUrl": "https://api.infusionsoft.com/crm/rest/v1/contacts/123", "timestamp": "..." }
  ]
}
```

- Deliveries are **batched**: up to **1,000 changed objects** of the same event type in
  one POST. Iterate `object_keys`; never assume one event per request.
- The payload is a **notification, not the record.** It carries ids and an optional
  `apiUrl`. Fetch the current state yourself — and budget those fetches against your
  rate limit, because a 1,000-object batch can become 1,000 GETs.
- Respond within **30 seconds** with a 2xx or 3xx status.

## 5. Retry and deactivation semantics

Keap attempts each delivery up to four times:

| Attempt | Timing |
|---|---|
| 1 | 30–60s after the change (5–10 **minutes** for `contactGroup.applied` and `contactGroup.delete`) |
| 2 | 30–60s after the previous failure |
| 3 | 5 minutes after the previous failure |
| 4 | 30 minutes after the previous failure |

A failure is: no response within 30 seconds, or a status `<200` or `>=400`.

- Returning **410 Gone at any time immediately marks the subscription Inactive.** Only
  return 410 when you actually mean "stop sending".
- After the fourth failed attempt the subscription goes Inactive.
- Recover by calling `verify_a_hook_subscription` — `POST /rest/v1/hooks/{key}/verify` —
  and completing the handshake again.

Audit your estate with `list_stored_hook_subscriptions` — `GET /rest/v1/hooks` — on a
schedule; an Inactive subscription fails silently otherwise.

## Signing

Keap documents `X-Hook-Secret` for **verification only**. It publishes no signing
algorithm or shared-secret derivation for event deliveries. Do not assume deliveries
are signed — authenticate them by re-fetching the referenced records over the API.

## Maintenance

- `update_a_hook_subscription` — `PUT /rest/v1/hooks/{key}`
- `delete_a_hook_subscription` — `DELETE /rest/v1/hooks/{key}`

## References

- AsyncAPI: `asyncapi/keap-resthooks-asyncapi.yml`
- Spec: `openapi/keap-rest-hooks-v1-api-openapi.yml`
- Docs: https://developer.infusionsoft.com/rest-hook-documentation/
