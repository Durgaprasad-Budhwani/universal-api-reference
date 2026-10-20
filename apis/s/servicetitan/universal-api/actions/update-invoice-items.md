# ServiceTitan: Update Invoice Items



```
PUT https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-invoice-items
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-invoice-items" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "invoiceId": 1,
  "description": "string",
  "quantity": 1
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-invoice-items', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "invoiceId": 1,
    "description": "string",
    "quantity": 1
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `invoiceId` | number | yes |  |
| `description` | string | yes |  |
| `quantity` | number | yes |  |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `skuId` | number | no |  |
| `skuName` | string | no |  |
| `technicianId` | number | no |  |
| `unitPrice` | number | no |  |
| `cost` | number | no |  |
| `isAddOn` | boolean | no |  |
| `signature` | string | no |  |
| `technicianAcknowledgementSignature` | string | no |  |
| `installedOn` | date | no |  |
| `inventoryWarehouseName` | string | no |  |
| `skipUpdatingMembershipPrices` | boolean | no |  |
| `itemGroupName` | string | no |  |
| `itemGroupRootId` | number | no |  |
| `inventoryLocationId` | number | no |  |
| `durationBillingId` | number | no |  |
| `budgetCodeId` | number | no |  |
| `id` | number | no |  |
| `serviceDate` | date | no |  |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native ServiceTitan API returns.

## Native endpoint

Through the native ServiceTitan API, this operation is `PATCH accounting/v2/tenant/{{credentials.tenant}}/invoices/:invoiceId/items` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/update-invoice-items.md) for the provider-specific parameters and requirements.

