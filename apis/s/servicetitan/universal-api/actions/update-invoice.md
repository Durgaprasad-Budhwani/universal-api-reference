# ServiceTitan: Update Invoice



```
PUT https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-invoice
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-invoice" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "id": 1,
  "items[].description": "string",
  "items[].quantity": 1,
  "payments[].id": 1
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-invoice', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "id": 1,
    "items[].description": "string",
    "items[].quantity": 1,
    "payments[].id": 1
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | number | yes |  |
| `items[]` | array<object> | no |  |
| `items[].description` | string | yes |  |
| `items[].quantity` | number | yes |  |
| `payments[].id` | number | yes |  |

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
| `dueDate` | date | no | Example: `2026-10-19`. |
| `payments[]` | array<object> | no |  |
| `payments[].settlementStatus` | list<string> | no | One of: `NotSettled`, `Settled`. |
| `payments[].settlementDate` | date | no |  |
| `rateSheetId` | number | no | Omit to leave the invoice's rate sheet unchanged. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native ServiceTitan API returns.

## Native endpoint

Through the native ServiceTitan API, this operation is `PATCH accounting/v2/tenant/{{credentials.tenant}}/invoices/:id` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/update-invoice.md) for the provider-specific parameters and requirements.

