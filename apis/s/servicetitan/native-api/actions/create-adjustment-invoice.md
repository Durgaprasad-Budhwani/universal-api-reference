# Create Adjustment Invoice with ServiceTitan

## Endpoint

- **Method:** `POST`
- **Path:** `accounting/v2/tenant/{tenant}/invoices`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Create Adjustment Invoice](https://developer.servicetitan.io/docs/apis/tenant-accounting-v2/endpoints/Invoices_CreateAdjustmentInvoice)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `adjustmentToId` | body | `number` | yes | — |
| `number` | body | `string` | no | — |
| `typeId` | body | `number` | no | — |
| `invoicedOn` | body | `date` | no | — |
| `subtotal` | body | `number` | no | — |
| `tax` | body | `number` | no | — |
| `taxZoneId` | body | `number` | no | — |
| `summary` | body | `string` | no | — |
| `royaltyStatus` | body | `list<string>` | no | Accepted values: `Failed`, `Pending`, `Sent`. |
| `royaltyDate` | body | `date` | no | — |
| `royaltySentOn` | body | `date` | no | — |
| `royaltyMemo` | body | `string` | no | — |
| `exportId` | body | `string` | no | — |
| `reviewStatus` | body | `list<string>` | no | Accepted values: `Invoiced`, `NeedsReview`, `OnHold`, `PendingApproval`, `ReadyForBilling`, `Rejected`, `Reviewed`. |
| `assignedToId` | body | `number` | no | — |
| `budgetCodeId` | body | `number` | no | — |
| `items[]` | body | `array<object>` | no | — |
| `items[].skuId` | body | `number` | no | — |
| `items[].skuName` | body | `string` | no | — |
| `items[].technicianId` | body | `number` | no | — |
| `items[].description` | body | `string` | yes | — |
| `items[].quantity` | body | `number` | yes | — |
| `items[].unitPrice` | body | `number` | no | — |
| `items[].cost` | body | `number` | no | — |
| `items[].isAddOn` | body | `boolean` | no | — |
| `items[].signature` | body | `string` | no | — |
| `items[].technicianAcknowledgementSignature` | body | `string` | no | — |
| `items[].installedOn` | body | `date` | no | — |
| `items[].inventoryWarehouseName` | body | `string` | no | — |
| `items[].skipUpdatingMembershipPrices` | body | `boolean` | no | — |
| `items[].itemGroupName` | body | `string` | no | — |
| `items[].itemGroupRootId` | body | `number` | no | — |
| `items[].inventoryLocationId` | body | `number` | no | — |
| `items[].durationBillingId` | body | `number` | no | — |
| `items[].budgetCodeId` | body | `number` | no | — |
| `items[].id` | body | `number` | no | — |
| `items[].serviceDate` | body | `date` | no | — |
