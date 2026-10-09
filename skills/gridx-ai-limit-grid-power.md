---
name: gridx-ai-limit-grid-power
description: Set or clear import/export power limits on a system gateway (e.g. peak shaving or grid-operator curtailment).
api: gridx-ai:gridx-api
operations:
- getSystemGatewayImportPowerLimit
- setSystemGatewayImportPowerLimit
- deleteSystemGatewayImportPowerLimit
- getSystemGatewayExportPowerLimit
- setSystemGatewayExportPowerLimit
- deleteSystemGatewayExportPowerLimit
generated: '2026-10-09'
method: generated
source: openapi/gridx-ai-openapi.yml
---

# Set or clear import/export power limits on a system gateway (e.g. peak shaving or grid-operator curtailment).

Authenticate every call with the `Authorization` header: `Bearer <JWT>` or `Token <api-token>` (HeaderAuth in the spec). Base URL `https://api.gridx.de`.

## Steps

1. `getSystemGatewayImportPowerLimit` / `getSystemGatewayExportPowerLimit` to read the current limit.
2. `setSystemGatewayImportPowerLimit` / `setSystemGatewayExportPowerLimit` (PUT) to apply a limit.
3. `deleteSystemGatewayImportPowerLimit` / `deleteSystemGatewayExportPowerLimit` to remove it.

## Retries and errors

PUT and DELETE are idempotent by HTTP semantics; these calls change physical asset behaviour, so confirm with a human before writing. No idempotency-key header is documented in the spec.
