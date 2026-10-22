# List Technician Skills with ServiceTitan

## Endpoint

- **Method:** `GET`
- **Path:** `dispatch/v2/tenant/{tenant}/technician-skills`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [List Technician Skills](https://developer.servicetitan.io/docs/apis/tenant-dispatch-v2/endpoints)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `technicianId` | query | `number` | no | The technician whose skills to return. Use Get Technicians to find the technician ID. |
| `includeTotal` | query | `boolean` | no | Include the total number of matching technician skills. |
| `active` | query | `list<string>` | no | Choose active skills, inactive skills, or both. Only active skills are returned when left empty. Accepted values: `Any`, `False`, `True`. |
| `createdBefore` | query | `date` | no | Return skills created before this date and time in UTC. |
| `createdOnOrAfter` | query | `date` | no | Return skills created on or after this date and time in UTC. |
| `modifiedBefore` | query | `date` | no | Return skills modified before this date and time in UTC. |
| `modifiedOnOrAfter` | query | `date` | no | Return skills modified on or after this date and time in UTC. |
| `sort` | query | `string` | no | Sort by Id, CreatedOn, or ModifiedOn. Use + for ascending order or - for descending order, for example -ModifiedOn. |
