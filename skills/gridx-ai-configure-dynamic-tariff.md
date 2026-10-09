---
name: gridx-ai-configure-dynamic-tariff
description: Set a system tariff and time-of-use optimisation settings, then inspect the resulting prices and decisions.
api: gridx-ai:gridx-api
operations:
- getSystemTariff
- setSystemTariff
- listSystemTariffPrices
- getSystemTimeOfUseReadiness
- setSystemTimeOfUseSettings
- getSystemTimeOfUseDecisions
generated: '2026-10-09'
method: generated
source: openapi/gridx-ai-openapi.yml
---

# Set a system tariff and time-of-use optimisation settings, then inspect the resulting prices and decisions.

Authenticate every call with the `Authorization` header: `Bearer <JWT>` or `Token <api-token>` (HeaderAuth in the spec). Base URL `https://api.gridx.de`.

## Steps

1. `getSystemTariff` to read the current tariff (v2).
2. `setSystemTariff` to set it; `listSystemTariffPrices` to confirm the price series.
3. `getSystemTimeOfUseReadiness` to check the system can run time-of-use optimisation.
4. `setSystemTimeOfUseSettings` (PUT, full replace) to enable/configure it.
5. `getSystemTimeOfUseDecisions` to see the optimiser's decisions.

## Retries and errors

`setSystemTariff` is a POST: read back with `getSystemTariff` before retrying. PUT settings calls replace state and are repeatable. No idempotency-key header is documented in the spec.
