# Create Technician Skill with ServiceTitan

## Endpoint

- **Method:** `POST`
- **Path:** `dispatch/v2/tenant/{tenant}/technician-skills`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Create Technician Skill](https://developer.servicetitan.io/docs/apis/tenant-dispatch-v2/endpoints)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `technicianId` | body | `number` | yes | The technician to assign the new skill to. Use Get Technicians to find the technician ID. |
| `name` | body | `string` | yes | The name of the new skill. |
| `active` | body | `boolean` | yes | Whether the new skill is active. |
