# Update Purchase Order with ServiceTitan

## Endpoint

- **Method:** `PATCH`
- **Path:** `inventory/v2/tenant/{tenant}/purchase-orders/:id`
- **Base URL:** `https://{baseUrl}/`
- **Official documentation:** [Update Purchase Order](https://developer.servicetitan.io/docs/apis/tenant-inventory-v2/endpoints/PurchaseOrders_Update)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `id` | path | `number` | yes | ServiceTitan purchase order ID to update. |
| `items[].id` | body | `number` | yes | ID of the purchase order item to update. |
| `shipTo.address.street` | body | `string` | no | Street. |
| `shipTo.description` | body | `string` | no | Description of the shipping address, such as a customer address or technician truck. |
| `items[].skuId` | body | `number` | yes | ID of the SKU from the pricebook. It can be any active material or equipment. |
| `shipTo.address` | body | `object` | no | Actual shipping address. |
| `shipTo.address.unit` | body | `string` | no | Unit. |
| `vendorId` | body | `number` | no | Id of the vendor for this purchase order. |
| `items[].description` | body | `string` | yes | Item description. |
| `shipTo.address.city` | body | `string` | no | City. |
| `typeId` | body | `number` | no | Id of the purchase order type for this purchase order. |
| `businessUnitId` | body | `number` | no | Id of the business unit for this purchase order. |
| `items[].vendorPartNumber` | body | `string` | yes | Part number of this item for the current vendor. |
| `shipTo.address.state` | body | `string` | no | State. |
| `inventoryLocationId` | body | `number` | no | Id of the inventory location for this purchase order. |
| `items[].quantity` | body | `number` | yes | Item quantity. |
| `shipTo.address.zip` | body | `string` | no | Zip code. |
| `items[].cost` | body | `number` | yes | Item cost. |
| `jobId` | body | `number` | no | Id of the job for this purchase order. Omit for a non-job purchase order. |
| `shipTo.address.country` | body | `string` | no | Country code. |
| `items[].budgetCodeId` | body | `number` | no | ID of the budget code for this purchase order item. |
| `technicianId` | body | `number` | no | Id of the technician for this purchase order. |
| `projectId` | body | `number` | no | Id of the project for this purchase order. |
| `budgetCodeId` | body | `number` | no | Id of the budget code for this purchase order. |
| `shipTo` | body | `object` | no | Address where the purchase order will be shipped. |
| `vendorInvoiceNumber` | body | `string` | no | Vendor invoice number. |
| `impactsTechnicianPayroll` | body | `boolean` | no | Whether this purchase order affects technician payroll. |
| `memo` | body | `string` | no | Summary or memo for this purchase order. |
| `date` | body | `date` | no | Purchase order date. |
| `requiredOn` | body | `date` | no | Date the purchase order is required. |
| `tax` | body | `number` | no | Tax amount. |
| `shipping` | body | `number` | no | Shipping cost. |
| `items[]` | body | `array<object>` | no | New or updated purchase order items. Sending this field replaces the active item set: active items omitted from the list are marked inactive. |
