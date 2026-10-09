---
name: gridx-ai-subscribe-webhooks
description: Create, test and maintain account webhook subscriptions.
api: gridx-ai:gridx-api
operations:
- listWebhookSubscriptions
- createWebhookSubscription
- pingWebhookSubscription
- rotateWebhookSubscriptionSecret
- deleteWebhookSubscription
generated: '2026-10-09'
method: generated
source: openapi/gridx-ai-openapi.yml
---

# Create, test and maintain account webhook subscriptions.

Authenticate every call with the `Authorization` header: `Bearer <JWT>` or `Token <api-token>` (HeaderAuth in the spec). Base URL `https://api.gridx.de`.

## Steps

1. `listWebhookSubscriptions` to avoid duplicates.
2. `createWebhookSubscription` for the account.
3. `pingWebhookSubscription` to verify delivery to your endpoint.
4. `rotateWebhookSubscriptionSecret` to rotate the signing secret; `deleteWebhookSubscription` to remove.

## Retries and errors

Create is a POST: list before retrying a failed create to avoid duplicate subscriptions. No idempotency-key header is documented in the spec.
