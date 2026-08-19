---
name: keap-order-and-subscription-billing
description: >-
  Sell through Keap: build a product catalogue, place a one-off order, take a payment
  through Keap's required hosted payment component, and stand up or cancel a recurring
  subscription plan.
api: Keap REST v2
version: v2
base_url: https://api.infusionsoft.com/crm/rest/v2
generated: '2026-08-13'
method: generated
source: openapi/_original/keap-v2-openapi.json
operations:
  - listOrders
  - createOrder
  - createOrderItem
  - listOrderPayments
  - createPaymentForAnOrder
  - attachFileToOrder
  - listSubscriptions
  - createSubscription
  - getSubscription
  - updateSubscription
  - invoiceSubscription
  - cancelSubscription
  - listSubscriptionPlans
  - createSubscriptionPlans
  - listOrderTotalDiscounts
  - createOrderTotalDiscount
---

# Take an order or start a subscription in Keap

All operationIds are verified against Keap's published v2 OpenAPI. Do not invent
operations. Every write below is **non-idempotent** — Keap publishes no idempotency
key — so a blind retry can double-charge or double-book. Read step 0 first.

## 0. The retry rule

Keap tells integrators to retry with exponential backoff on 429, but supplies no
idempotency mechanism. Before retrying any `create*` in this skill:

1. Re-run the matching `list*` operation filtered to the record you were creating.
2. Only retry if it is genuinely absent.

This is the single highest-risk property of the Keap commerce API.

## 1. Catalogue

- `listProducts` / `createProduct` under `/rest/v2/products` establish what you can sell.
- `createSubscriptionPlans` — `POST /rest/v2/products/{product_id}/subscriptions` —
  attaches a recurring plan to a product. `listSubscriptionPlans` reads them back.

## 2. One-off order

1. `createOrder` — `POST /rest/v2/orders`.
2. `createOrderItem` — `POST /rest/v2/orders/{order_id}/items` — add line items.
3. Optionally `attachFileToOrder` — `POST /rest/v2/orders/{order_id}:attachFile` — to
   put a document on the invoice. `detachFileFromOrder` reverses it.
4. `listOrders` — `GET /rest/v2/orders` — paginate with `page_size`/`page_token`,
   filter and `order_by` as usual.

Discounts are separate resources, not order fields. `listOrderTotalDiscounts` /
`createOrderTotalDiscount` under `/rest/v2/discounts/orderTotals` cover order-total
discounts; there are parallel families for product, category, shipping and free-trial
discounts.

## 3. Payment — you must use the hosted component

Keap states that **to use any of its payment processors you are required to use Keap's
hosted payment component**. Card data never goes through the REST API.

1. `POST /rest/v2/paymentMethodConfigs` with `{"contact_id": <id>}` → returns a
   `session_key`. It expires in **one hour**.
2. In the browser, load `https://payments.keap.page/lib/payment-method-embed.js` and
   render `<keap-payment-method data-key="SESSION_KEY">`. Style it with `data-styles`.
   Note the loader URL is unpinned — you cannot select a build.
3. `createPaymentForAnOrder` — `POST /rest/v2/orders/{order_id}/payments` — record the
   payment against the order. `listOrderPayments` reads payments back.

Processors brokered by the component: Stripe, PayPal, Authorize.Net.

## 4. Subscriptions

- `createSubscription` — `POST /rest/v2/subscriptions`.
- `getSubscription` / `listSubscriptions` to read.
- `updateSubscription` — `PATCH /rest/v2/subscriptions/{subscription_id}` — remember
  the `update_mask` query parameter; omitted fields are untouched.
- `invoiceSubscription` — `POST /rest/v2/subscriptions/{subscription_id}:invoice` —
  bill the subscription now.
- `cancelSubscription` — `POST /rest/v2/subscriptions/{subscription_id}:deactivate`.
  Note the operationId says "cancel" but the path segment says `:deactivate`; they are
  the same call.

## What you cannot do

Keap's own FAQ states plainly: **refunds cannot be issued through the API.** Do not
attempt to synthesise one from payment or order operations — route the customer to the
Keap application.

## Errors and limits

- Uniform error set on every operation: 400, 401, 403, 404, 405, 409, 500, 501 with
  `{code, message, status, details[]}` as `application/json` (not RFC 9457).
- 409 Conflict is declared everywhere but, without an idempotency key, cannot be relied
  on to distinguish a duplicate submission from a real state conflict.
- 429 is undeclared but real. See `rate-limits/keap-rate-limits.yml`.

## References

- Components: `components/keap-components.yml`
- Conventions: `conventions/keap-conventions.yml`
- Data model: `data-model/keap-data-model.yml`
- Spec: `openapi/keap-orders-api-openapi.yml`, `openapi/keap-subscriptions-api-openapi.yml`
