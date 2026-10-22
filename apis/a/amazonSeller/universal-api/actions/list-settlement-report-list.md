# Amazon Seller: List Settlement Report List

Retrieves Settlement reports from Amazon Seller.

```
GET https://connect.mindcloud.co/v1/universal/amazonSeller/latest/actions/list-settlement-report-list
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Amazon Seller `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/amazonSeller/latest/actions/list-settlement-report-list?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/amazonSeller/latest/actions/list-settlement-report-list?${params}`, {
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
| `reportType` | list | no | One of: `GET_V2_SETTLEMENT_REPORT_DATA_FLAT_FILE_V2`. |
| `processingStatuses` | list | no | One of: `CANCELLED`, `DONE`, `FATAL`, `IN_PROGRESS`, `IN_QUEUE`. Accepts multiple values as an array. |
| `createdSince` | string | no |  |
| `createdUntil` | string | no |  |
| `marketplaces` | list | no | One of: `A1AM78C64UM0Y8`, `A2EUQ1WTGCTBG2`, `ATVPDKIKX0DER`. Accepts multiple values as an array. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "createdTime": "string",
      "dataEndTime": "string",
      "dataStartTime": "string",
      "marketplaceIds": [
        "string"
      ],
      "processingEndTime": "string",
      "processingStartTime": "string",
      "processingStatus": "string",
      "reportDocumentId": "string",
      "reportId": "string",
      "reportType": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `createdTime` | string |  |
| `dataEndTime` | string |  |
| `dataStartTime` | string |  |
| `marketplaceIds` | array<string> |  |
| `processingEndTime` | string |  |
| `processingStartTime` | string |  |
| `processingStatus` | string |  |
| `reportDocumentId` | string |  |
| `reportId` | string |  |
| `reportType` | string |  |

## Native endpoint

Through the native Amazon Seller API, this operation is `GET reports/2021-06-30/reports` (base URL `https://{{credentials.environment}}-{{credentials.region}}.amazon.com`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-settlement-report-list.md) for the provider-specific parameters and requirements.

