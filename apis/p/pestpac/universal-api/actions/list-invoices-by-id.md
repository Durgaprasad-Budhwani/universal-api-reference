# PestPac: List Invoices by ID



```
GET https://connect.mindcloud.co/v1/universal/pestpac/latest/actions/list-invoices-by-id
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a PestPac `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/pestpac/latest/actions/list-invoices-by-id?connectionId=$CONNECTION_ID&id=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "id": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/pestpac/latest/actions/list-invoices-by-id?${params}`, {
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
| `id` | string | yes |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "balance": 1,
      "billTo": {
        "address": "string",
        "address2": "string",
        "city": "string",
        "company": "string",
        "fName": "Ava Chen",
        "lName": "Ava Chen",
        "state": "string",
        "title": "string",
        "zip": "string"
      },
      "billToID": 1,
      "branch": "string",
      "branchID": 1,
      "cost": 1,
      "description": "string",
      "dueDate": "string",
      "duration": 1,
      "invoiceDate": "string",
      "invoiceID": 1,
      "invoiceNumber": "string",
      "invoiceType": "string",
      "locationID": 1,
      "orderDate": "string",
      "orderNumber": "string",
      "orderType": "string",
      "origin": "string",
      "serviceCode": "string",
      "serviceFeeTotal": 1,
      "serviceLocation": {
        "address": "string",
        "address2": "string",
        "city": "string",
        "company": "string",
        "fName": "Ava Chen",
        "lName": "Ava Chen",
        "state": "string",
        "title": "string",
        "zip": "string"
      },
      "setupID": 1,
      "setupType": "string",
      "subTotal": 1,
      "tax": 1,
      "taxDetails": [
        {
          "countryOfTax": "string",
          "taxAmount": 1,
          "taxLabel": "string",
          "taxRate": 1
        }
      ],
      "taxRate": 1,
      "timeRange": "string",
      "total": 1,
      "workDate": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `balance` | number |  |
| `billTo` | object |  |
| `billTo.address` | string |  |
| `billTo.address2` | string |  |
| `billTo.city` | string |  |
| `billTo.company` | string |  |
| `billTo.fName` | string |  |
| `billTo.lName` | string |  |
| `billTo.state` | string |  |
| `billTo.title` | string |  |
| `billTo.zip` | string |  |
| `billToID` | number |  |
| `branch` | string |  |
| `branchID` | number |  |
| `cost` | number |  |
| `description` | string |  |
| `dueDate` | string |  |
| `duration` | number |  |
| `invoiceDate` | string |  |
| `invoiceID` | number |  |
| `invoiceNumber` | string |  |
| `invoiceType` | string |  |
| `locationID` | number |  |
| `orderDate` | string |  |
| `orderNumber` | string |  |
| `orderType` | string |  |
| `origin` | string |  |
| `serviceCode` | string |  |
| `serviceFeeTotal` | number |  |
| `serviceLocation` | object |  |
| `serviceLocation.address` | string |  |
| `serviceLocation.address2` | string |  |
| `serviceLocation.city` | string |  |
| `serviceLocation.company` | string |  |
| `serviceLocation.fName` | string |  |
| `serviceLocation.lName` | string |  |
| `serviceLocation.state` | string |  |
| `serviceLocation.title` | string |  |
| `serviceLocation.zip` | string |  |
| `setupID` | number |  |
| `setupType` | string |  |
| `subTotal` | number |  |
| `tax` | number |  |
| `taxDetails` | array<object> |  |
| `taxDetails[].countryOfTax` | string |  |
| `taxDetails[].taxAmount` | number |  |
| `taxDetails[].taxLabel` | string |  |
| `taxDetails[].taxRate` | number |  |
| `taxRate` | number |  |
| `timeRange` | string |  |
| `total` | number |  |
| `workDate` | string |  |

## Native endpoint

Through the native PestPac API, this operation is `GET Invoices/:id` (base URL `https://api.workwave.com/pestpac/v1/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-invoices-by-id.md) for the provider-specific parameters and requirements.

