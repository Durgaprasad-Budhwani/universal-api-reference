# ServiceTitan: Get Returns



```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-returns
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-returns?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-returns?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as query string parameters ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `modifiedOnOrAfter` | string | no | Returns modified on or after this UTC timestamp. |
| `syncStatuses` | string | no | Sync status collection filter: Pending, Posted, or Exported. Accepts multiple values in one string, delimited by `,`. |
| `active` | list<string> | no | Active-state filter: True, Any, or False. One of: `Any`, `False`, `True`. |
| `ids` | string | no | Return IDs to retrieve, up to 50. Accepts multiple values in one string, delimited by `,`. |
| `number` | string | no | Return number filter. |
| `referenceNumber` | string | no | Reference number filter. |
| `jobId` | number | no | Job ID filter. |
| `purchaseOrderId` | number | no | Purchase order ID filter. |
| `batchId` | number | no | Batch ID filter. |
| `vendorIds` | string | no | Vendor ID collection filter. Accepts multiple values in one string, delimited by `,`. |
| `businessUnitIds` | string | no | Business unit ID collection filter. Accepts multiple values in one string, delimited by `,`. |
| `inventoryLocationIds` | string | no | Inventory location ID collection filter. Accepts multiple values in one string, delimited by `,`. |
| `returnDateOnOrAfter` | string | no | Returns with a return date on or after this timestamp. |
| `returnDateBefore` | string | no | Returns with a return date before this timestamp. |
| `createdOnOrAfter` | string | no | Returns created on or after this UTC timestamp. |
| `createdBefore` | string | no | Returns created before this UTC timestamp. |
| `modifiedBefore` | string | no | Returns modified before this UTC timestamp. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `customFields.Fields` | object | no | Custom-field name and value pairs to filter by. |
| `customFields.Operator` | list<string> | no | How custom-field filters are combined: And or Or. One of: `And`, `Or`. |
| `page` | number | no | Page number, starting from 1. |
| `pageSize` | number | no | Number of records per page; ServiceTitan defaults to 50. |
| `includeTotal` | boolean | no | Whether to include the total matching record count. |
| `sort` | list<string> | no | Sort by Id, CreatedOn, or ModifiedOn. Prefix with + for ascending or - for descending. One of: `+CreatedOn`, `+Id`, `+ModifiedOn`, `-CreatedOn`, `-Id`, `-ModifiedOn`. |
| `externalDataApplicationGuid` | string | no | Application GUID whose external data should be returned. |
| `externalDataKey` | string | no | External data key; requires External Data Values. |
| `externalDataValues` | string | no | External data values; requires External Data Key and accepts up to 50. Accepts multiple values in one string, delimited by `,`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "active": true,
      "batch": {
        "id": 1,
        "name": "Ava Chen",
        "number": "string"
      },
      "batchId": 1,
      "budgetCodeId": 1,
      "businessUnitId": 1,
      "canceledById": 1,
      "canceledReason": "string",
      "createdById": 1,
      "createdOn": "string",
      "creditReceivedOn": "string",
      "customFields": {},
      "dateCanceled": "string",
      "externalData": {},
      "id": 1,
      "inventoryLocationId": 1,
      "items": [
        {
          "active": true,
          "assetAccount": {
            "detailType": "string",
            "name": "Ava Chen",
            "number": "string",
            "type": "string"
          },
          "budgetCodeId": 1,
          "code": "string",
          "cost": 1,
          "costOfSaleAccount": {
            "detailType": "string",
            "name": "Ava Chen",
            "number": "string",
            "type": "string"
          },
          "createdById": 1,
          "createdOn": "string",
          "description": "string",
          "generalLedgerAccount": {
            "detailType": "string",
            "name": "Ava Chen",
            "number": "string",
            "type": "string"
          },
          "id": 1,
          "modifiedOn": "string",
          "name": "Ava Chen",
          "quantity": 1,
          "receiptItemId": 1,
          "serialNumbers": [
            "string"
          ],
          "skuId": 1
        }
      ],
      "jobId": 1,
      "memo": "string",
      "modifiedOn": "string",
      "number": "string",
      "projectId": 1,
      "purchaseOrderId": 1,
      "referenceNumber": "string",
      "returnAmount": 1,
      "returnDate": "string",
      "returnedOn": "string",
      "returnTypeId": 1,
      "shippingAmount": 1,
      "status": "string",
      "syncStatus": "string",
      "taxAmount": 1,
      "vendorId": 1
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `active` | boolean |  |
| `batch` | object |  |
| `batch.id` | number |  |
| `batch.name` | string |  |
| `batch.number` | string |  |
| `batchId` | number |  |
| `budgetCodeId` | number |  |
| `businessUnitId` | number |  |
| `canceledById` | number |  |
| `canceledReason` | string |  |
| `createdById` | number |  |
| `createdOn` | string |  |
| `creditReceivedOn` | string |  |
| `customFields` | object |  |
| `dateCanceled` | string |  |
| `externalData` | object |  |
| `id` | number |  |
| `inventoryLocationId` | number |  |
| `items` | array<object> |  |
| `items[].active` | boolean |  |
| `items[].assetAccount` | object |  |
| `items[].assetAccount.detailType` | string |  |
| `items[].assetAccount.name` | string |  |
| `items[].assetAccount.number` | string |  |
| `items[].assetAccount.type` | string |  |
| `items[].budgetCodeId` | number |  |
| `items[].code` | string |  |
| `items[].cost` | number |  |
| `items[].costOfSaleAccount` | object |  |
| `items[].costOfSaleAccount.detailType` | string |  |
| `items[].costOfSaleAccount.name` | string |  |
| `items[].costOfSaleAccount.number` | string |  |
| `items[].costOfSaleAccount.type` | string |  |
| `items[].createdById` | number |  |
| `items[].createdOn` | string |  |
| `items[].description` | string |  |
| `items[].generalLedgerAccount` | object |  |
| `items[].generalLedgerAccount.detailType` | string |  |
| `items[].generalLedgerAccount.name` | string |  |
| `items[].generalLedgerAccount.number` | string |  |
| `items[].generalLedgerAccount.type` | string |  |
| `items[].id` | number |  |
| `items[].modifiedOn` | string |  |
| `items[].name` | string |  |
| `items[].quantity` | number |  |
| `items[].receiptItemId` | number |  |
| `items[].serialNumbers` | array |  |
| `items[].skuId` | number |  |
| `jobId` | number |  |
| `memo` | string |  |
| `modifiedOn` | string |  |
| `number` | string |  |
| `projectId` | number |  |
| `purchaseOrderId` | number |  |
| `referenceNumber` | string |  |
| `returnAmount` | number |  |
| `returnDate` | string |  |
| `returnedOn` | string |  |
| `returnTypeId` | number |  |
| `shippingAmount` | number |  |
| `status` | string |  |
| `syncStatus` | string |  |
| `taxAmount` | number |  |
| `vendorId` | number |  |

## Native endpoint

Through the native ServiceTitan API, this operation is `GET inventory/v2/tenant/{{credentials.tenant}}/returns` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/get-returns.md) for the provider-specific parameters and requirements.

