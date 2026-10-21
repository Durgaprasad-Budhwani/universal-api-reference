# ServiceTitan: Update Purchase Order



```
PUT https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-purchase-order
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-purchase-order" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "id": 1,
  "items[].id": 1,
  "items[].skuId": 1,
  "items[].description": "string",
  "items[].vendorPartNumber": "string",
  "items[].quantity": 1,
  "items[].cost": 1
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-purchase-order', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "id": 1,
    "items[].id": 1,
    "items[].skuId": 1,
    "items[].description": "string",
    "items[].vendorPartNumber": "string",
    "items[].quantity": 1,
    "items[].cost": 1
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | number | yes | ServiceTitan purchase order ID to update. |
| `items[].id` | number | yes | ID of the purchase order item to update. |
| `shipTo.address.street` | string | no | Street. |
| `shipTo.description` | string | no | Description of the shipping address, such as a customer address or technician truck. |
| `items[].skuId` | number | yes | ID of the SKU from the pricebook. It can be any active material or equipment. |
| `shipTo.address` | object | no | Actual shipping address. |
| `shipTo.address.unit` | string | no | Unit. |
| `vendorId` | number | no | Id of the vendor for this purchase order. |
| `items[].description` | string | yes | Item description. |
| `shipTo.address.city` | string | no | City. |
| `typeId` | number | no | Id of the purchase order type for this purchase order. |
| `businessUnitId` | number | no | Id of the business unit for this purchase order. |
| `items[].vendorPartNumber` | string | yes | Part number of this item for the current vendor. |
| `shipTo.address.state` | string | no | State. |
| `inventoryLocationId` | number | no | Id of the inventory location for this purchase order. |
| `items[].quantity` | number | yes | Item quantity. |
| `shipTo.address.zip` | string | no | Zip code. |
| `items[].cost` | number | yes | Item cost. |
| `jobId` | number | no | Id of the job for this purchase order. Omit for a non-job purchase order. |
| `shipTo.address.country` | string | no | Country code. |
| `technicianId` | number | no | Id of the technician for this purchase order. |
| `projectId` | number | no | Id of the project for this purchase order. |
| `budgetCodeId` | number | no | Id of the budget code for this purchase order. |
| `shipTo` | object | no | Address where the purchase order will be shipped. |
| `vendorInvoiceNumber` | string | no | Vendor invoice number. |
| `impactsTechnicianPayroll` | boolean | no | Whether this purchase order affects technician payroll. |
| `memo` | string | no | Summary or memo for this purchase order. |
| `date` | date | no | Purchase order date. |
| `requiredOn` | date | no | Date the purchase order is required. |
| `tax` | number | no | Tax amount. |
| `shipping` | number | no | Shipping cost. |
| `items[]` | array<object> | no | New or updated purchase order items. Sending this field replaces the active item set: active items omitted from the list are marked inactive. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `items[].budgetCodeId` | number | no | ID of the budget code for this purchase order item. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native ServiceTitan API returns.

## Native endpoint

Through the native ServiceTitan API, this operation is `PATCH inventory/v2/tenant/{{credentials.tenant}}/purchase-orders/:id` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/update-purchase-order.md) for the provider-specific parameters and requirements.

