# Assign Technician Skills with ServiceTitan

## Endpoint

- **Method:** `PATCH`
- **Path:** `dispatch/v2/tenant/{tenant}/technician-skills`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Assign Technician Skills](https://developer.servicetitan.io/docs/apis/tenant-dispatch-v2/endpoints)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `technicianId` | body | `number` | yes | The technician to assign existing skills to. Use Get Technicians to find the technician ID. |
| `skillIds[]` | body | `array<number>` | yes | The numeric IDs of the existing skills to assign to the technician. |
| `replaceExistingSkills` | body | `boolean` | yes | True replaces all of the technician's current skills and removes skills not in this list. False adds these skills while keeping the technician's current skills. |
