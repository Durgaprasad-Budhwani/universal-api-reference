# Update Invoice with ServiceTitan

## Endpoint

- **Method:** `PATCH`
- **Path:** `accounting/v2/tenant/{tenant}/invoices/:id`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Update Invoice](https://tenant-api-credentials-portal-integration.servicetitan.io/docs/apis/tenant-accounting-v2/endpoints/Invoices_UpdateInvoice)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `id` | path | `number` | yes | — |
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
| `dueDate` | body | `date` | no | — |
| `payments[]` | body | `array<object>` | no | — |
| `payments[].id` | body | `number` | yes | — |
| `payments[].settlementStatus` | body | `list<string>` | no | Accepted values: `NotSettled`, `Settled`. |
| `payments[].settlementDate` | body | `date` | no | — |
| `rateSheetId` | body | `number` | no | Omit to leave the invoice's rate sheet unchanged. |
