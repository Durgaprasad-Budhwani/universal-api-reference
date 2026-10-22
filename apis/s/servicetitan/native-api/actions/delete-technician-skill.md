# Delete Technician Skill with ServiceTitan

## Endpoint

- **Method:** `DELETE`
- **Path:** `dispatch/v2/tenant/{tenant}/technician-skills/:id`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Delete Technician Skill](https://developer.servicetitan.io/docs/apis/tenant-dispatch-v2/endpoints)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `id` | path | `string` | yes | The technician skill ID, formatted {TechnicianId}_{SkillId}, as returned by List Technician Skills. |
