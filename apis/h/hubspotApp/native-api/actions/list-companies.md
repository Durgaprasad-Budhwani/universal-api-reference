# List Companies with HubSpot

Retrieves companies from HubSpot.

## Endpoint

- **Method:** `GET`
- **Path:** `crm/v3/objects/companies`
- **Base URL:** `https://api.hubapi.com`
- **API:** REST - Query Pagination
- **Official documentation:** [List Companies](https://developers.hubspot.com/docs/api-reference/crm-companies-v3/basic/get-crm-v3-objects-companies)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `properties[]` | query | `array<string>` | no | Company properties to return in the response. Send multiple values as a string separated by `,`. |
| `propertiesWithHistory[]` | query | `array<string>` | no | Company properties to return with value history. Send multiple values as a string separated by `,`. |
| `associations[]` | query | `array<string>` | no | Company-associated object types to include as associated IDs. Send multiple values as a string separated by `,`. |
| `archived` | query | `boolean` | no | Whether to return only archived company records. |
