# ServiceTitan: Create Adjustment Invoice



```
POST https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/create-adjustment-invoice
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/create-adjustment-invoice" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "adjustmentToId": 1,
  "items[].description": "string",
  "items[].quantity": 1
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/create-adjustment-invoice', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "adjustmentToId": 1,
    "items[].description": "string",
    "items[].quantity": 1
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `adjustmentToId` | number | yes |  |
| `items[]` | array<object> | no |  |
| `items[].description` | string | yes |  |
| `items[].quantity` | number | yes |  |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `number` | string | no |  |
| `typeId` | number | no |  |
| `invoicedOn` | date | no |  |
| `subtotal` | number | no |  |
| `tax` | number | no |  |
| `taxZoneId` | number | no |  |
| `summary` | string | no |  |
| `royaltyStatus` | list<string> | no | One of: `Failed`, `Pending`, `Sent`. |
| `royaltyDate` | date | no |  |
| `royaltySentOn` | date | no |  |
| `royaltyMemo` | string | no |  |
| `exportId` | string | no |  |
| `reviewStatus` | list<string> | no | One of: `Invoiced`, `NeedsReview`, `OnHold`, `PendingApproval`, `ReadyForBilling`, `Rejected`, `Reviewed`. |
| `assignedToId` | number | no |  |
| `budgetCodeId` | number | no |  |
| `items[].skuId` | number | no |  |
| `items[].skuName` | string | no |  |
| `items[].technicianId` | number | no |  |
| `items[].unitPrice` | number | no |  |
| `items[].cost` | number | no |  |
| `items[].isAddOn` | boolean | no |  |
| `items[].signature` | string | no |  |
| `items[].technicianAcknowledgementSignature` | string | no |  |
| `items[].installedOn` | date | no |  |
| `items[].inventoryWarehouseName` | string | no |  |
| `items[].skipUpdatingMembershipPrices` | boolean | no |  |
| `items[].itemGroupName` | string | no |  |
| `items[].itemGroupRootId` | number | no |  |
| `items[].inventoryLocationId` | number | no |  |
| `items[].durationBillingId` | number | no |  |
| `items[].budgetCodeId` | number | no |  |
| `items[].id` | number | no |  |
| `items[].serviceDate` | date | no |  |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native ServiceTitan API returns.

## Native endpoint

Through the native ServiceTitan API, this operation is `POST accounting/v2/tenant/{{credentials.tenant}}/invoices` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/create-adjustment-invoice.md) for the provider-specific parameters and requirements.

