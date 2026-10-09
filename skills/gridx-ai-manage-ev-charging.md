---
name: gridx-ai-manage-ev-charging
description: Manage EV profiles and charging schedules for a gridX system.
api: gridx-ai:gridx-api
operations:
- listSystemEVProfiles
- createSystemEVProfile
- updateSystemEVProfile
- listSystemEVChargingSchedules
- createSystemEVChargingSchedule
generated: '2026-10-09'
method: generated
source: openapi/gridx-ai-openapi.yml
---

# Manage EV profiles and charging schedules for a gridX system.

Authenticate every call with the `Authorization` header: `Bearer <JWT>` or `Token <api-token>` (HeaderAuth in the spec). Base URL `https://api.gridx.de`.

## Steps

1. `listSystemEVProfiles` to see existing EV profiles.
2. `createSystemEVProfile` (or `updateSystemEVProfile`) to define a vehicle profile.
3. `listSystemEVChargingSchedules` to see existing schedules.
4. `createSystemEVChargingSchedule` to add a schedule.

## Retries and errors

Create calls are POSTs: list first and check for an existing profile/schedule before retrying a failed create. No idempotency-key header is documented in the spec.
