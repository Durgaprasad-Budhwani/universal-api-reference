# Update Customer with ServiceTitan

Updates an existing customer in ServiceTitan.

## Endpoint

- **Method:** `PATCH`
- **Path:** `crm/v2/tenant/{tenant}/customers/:id`
- **Base URL:** `https://{baseUrl}/`

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `address.street` | body | `string` | no | — |
| `customFields[].typeId` | body | `number` | no | — |
| `externalData.applicationGuid` | body | `string` | no | — |
| `externalData.externalData[].key` | body | `string` | no | — |
| `name` | body | `string` | no | — |
| `address.unit` | body | `string` | no | — |
| `customFields[].value` | body | `string` | no | — |
| `externalData.externalData[]` | body | `array` | no | — |
| `externalData.externalData[].value` | body | `string` | no | — |
| `type` | body | `string` | no | Residential or commercial |
| `address` | body | `object<object>` | no | Bill-To address of the customer record |
| `address.city` | body | `string` | no | — |
| `address.state` | body | `string` | no | — |
| `customFields[]` | body | `array<object>` | no | — |
| `address.zip` | body | `string` | no | — |
| `externalData` | body | `object` | no | — |
| `address.country` | body | `string` | no | — |
| `doNotMail` | body | `boolean` | no | Format: `toggle`. |
| `id` | path | `string` | yes | — |
| `address.longitude` | body | `number` | no | — |
| `doNotService` | body | `boolean` | no | Format: `toggle`. |
| `active` | body | `boolean` | no | Customer has been flagged as “active” ar "innactive" |
| `address.latitude` | body | `number` | no | — |
| `tagTypeIds[]` | body | `array<number>` | no | — |
