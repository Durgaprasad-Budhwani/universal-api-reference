# Get Vendor Bills with ServiceTitan

Retrieves vendor bills from ServiceTitan.

## Endpoint

- **Method:** `GET`
- **Path:** `accounting/v2/tenant/{tenant}/inventory-bills`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Get Vendor Bills](https://developer.servicetitan.io/api-details/#api=tenant-accounting-v2&operation=Invoices_GetList)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `modifiedOnOrAfter` | query | `string` | no | — |
| `invoicedOnOrAfter` | query | `string` | no | — |
| `statuses` | query | `string` | no | Pending, Posted, Exported |
| `ids` | query | `string` | no | — |
| `number` | query | `string` | no | Reference number associated with invoices. |
| `orderBy` | query | `string` | no | — |
| `orderByDirection` | query | `string` | no | Order direction of the retuned list of invoices. Values of "desc" or "descending" will order the list in descending order, otherwise the list will be ordered in ascending order. |
| `customerId` | query | `string` | no | — |
| `totalGreater` | query | `number` | no | — |
| `totalLess` | query | `number` | no | — |
| `jobNumber` | query | `string` | no | — |
| `jobId` | query | `string` | no | — |
| `batchId` | query | `number` | no | Batch ID associated with invoices. |
| `batchNumber` | query | `number` | no | Batch number associated with invoices. |
