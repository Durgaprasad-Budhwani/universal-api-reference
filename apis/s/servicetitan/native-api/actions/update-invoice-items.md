# Update Invoice Items with ServiceTitan

## Endpoint

- **Method:** `PATCH`
- **Path:** `accounting/v2/tenant/{tenant}/invoices/:invoiceId/items`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Update Invoice Items](https://developer.servicetitan.io/docs/apis/tenant-accounting-v2/endpoints/Invoices_UpdateInvoiceItems)

## Parameters

| Parameter | Location | Type | Required |
| --- | --- | --- | --- |
| `invoiceId` | path | `number` | yes |
| `skuId` | body | `number` | no |
| `skuName` | body | `string` | no |
| `technicianId` | body | `number` | no |
| `description` | body | `string` | yes |
| `quantity` | body | `number` | yes |
| `unitPrice` | body | `number` | no |
| `cost` | body | `number` | no |
| `isAddOn` | body | `boolean` | no |
| `signature` | body | `string` | no |
| `technicianAcknowledgementSignature` | body | `string` | no |
| `installedOn` | body | `date` | no |
| `inventoryWarehouseName` | body | `string` | no |
| `skipUpdatingMembershipPrices` | body | `boolean` | no |
| `itemGroupName` | body | `string` | no |
| `itemGroupRootId` | body | `number` | no |
| `inventoryLocationId` | body | `number` | no |
| `durationBillingId` | body | `number` | no |
| `budgetCodeId` | body | `number` | no |
| `id` | body | `number` | no |
| `serviceDate` | body | `date` | no |
