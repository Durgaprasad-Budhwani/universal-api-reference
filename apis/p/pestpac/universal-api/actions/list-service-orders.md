# PestPac: List Service Orders



```
GET https://connect.mindcloud.co/v1/universal/pestpac/latest/actions/list-service-orders
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a PestPac `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/pestpac/latest/actions/list-service-orders?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/pestpac/latest/actions/list-service-orders?${params}`, {
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
| `startWorkDate` | string | no |  |
| `endWorkDate` | string | no |  |
| `posted` | boolean | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "batchNumber": 1,
      "billToID": 1,
      "branch": "string",
      "branchID": 1,
      "bundleName": "Ava Chen",
      "daysOfWeek": "string",
      "description": "string",
      "discountCode": "string",
      "duration": 1,
      "earliestDate": "string",
      "earliestTime": "string",
      "earliestTime2": "string",
      "externalIdentifier": "string",
      "inProgress": true,
      "latestDate": "string",
      "latestTime": "string",
      "latestTime2": "string",
      "leadID": 1,
      "locationBundleID": 1,
      "locationID": 1,
      "locationInstructions": "string",
      "locked": true,
      "orderID": 1,
      "orderInstructions": "string",
      "orderNumber": "string",
      "orderType": "string",
      "origin": "string",
      "parentOrderID": 1,
      "pdfUrls": [
        "https://example.com"
      ],
      "posted": true,
      "purchaseOrderNumber": "string",
      "route": "string",
      "serviceCode": "string",
      "serviceInstructions": "string",
      "setupID": 1,
      "subTotal": 1,
      "tax": 1,
      "taxDetails": [
        {}
      ],
      "tech1": "string",
      "techID1": 1,
      "technicianComment": "string",
      "timeRange": "string",
      "total": 1,
      "userDefinedFields": [
        {}
      ],
      "workDate": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `batchNumber` | number |  |
| `billToID` | number |  |
| `branch` | string |  |
| `branchID` | number |  |
| `bundleName` | string |  |
| `daysOfWeek` | string |  |
| `description` | string |  |
| `discountCode` | string |  |
| `duration` | number |  |
| `earliestDate` | string |  |
| `earliestTime` | string |  |
| `earliestTime2` | string |  |
| `externalIdentifier` | string |  |
| `inProgress` | boolean |  |
| `latestDate` | string |  |
| `latestTime` | string |  |
| `latestTime2` | string |  |
| `leadID` | number |  |
| `locationBundleID` | number |  |
| `locationID` | number |  |
| `locationInstructions` | string |  |
| `locked` | boolean |  |
| `orderID` | number |  |
| `orderInstructions` | string |  |
| `orderNumber` | string |  |
| `orderType` | string |  |
| `origin` | string |  |
| `parentOrderID` | number |  |
| `pdfUrls` | array<string> |  |
| `posted` | boolean |  |
| `purchaseOrderNumber` | string |  |
| `route` | string |  |
| `serviceCode` | string |  |
| `serviceInstructions` | string |  |
| `setupID` | number |  |
| `subTotal` | number |  |
| `tax` | number |  |
| `taxDetails` | array<object> |  |
| `tech1` | string |  |
| `techID1` | number |  |
| `technicianComment` | string |  |
| `timeRange` | string |  |
| `total` | number |  |
| `userDefinedFields` | array<object> |  |
| `workDate` | string |  |

## Native endpoint

Through the native PestPac API, this operation is `GET ServiceOrders` (base URL `https://api.workwave.com/pestpac/v1/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-service-orders.md) for the provider-specific parameters and requirements.

