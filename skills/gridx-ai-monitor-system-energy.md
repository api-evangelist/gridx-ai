---
name: gridx-ai-monitor-system-energy
description: Find a gridX system and read its live and historical energy measurements plus per-asset data.
api: gridx-ai:gridx-api
operations:
- listSystems
- getSystem
- getSystemLiveMeasurements
- getSystemHistoricalMeasurements
- listSystemAsset
- getAssetMeasurements
generated: '2026-10-09'
method: generated
source: openapi/gridx-ai-openapi.yml
---

# Find a gridX system and read its live and historical energy measurements plus per-asset data.

Authenticate every call with the `Authorization` header: `Bearer <JWT>` or `Token <api-token>` (HeaderAuth in the spec). Base URL `https://api.gridx.de`.

## Steps

1. `listSystems` to find the target system (or `getSystem` when the systemID is known).
2. `getSystemLiveMeasurements` for the current power flows.
3. `getSystemHistoricalMeasurements` for a time range of historic data.
4. `listSystemAsset` then `getAssetMeasurements` to drill into a single asset (PV, battery, heat pump, charger).

## Retries and errors

All steps are GET and safe to retry. No idempotency-key header is documented in the spec.
