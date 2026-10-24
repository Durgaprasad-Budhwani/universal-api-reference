# Epicor Prophet 21: List Quotes



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-quotes
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-quotes?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-quotes?${params}`, {
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

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `select` | string | no | Comma-separated field names. Leave empty to return all available fields. Default: `order_no,ship2_name,customer_id,projected_order,date_created,rma_expiration_date,location_id,approved,completed`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "approved": "string",
      "completed": "string",
      "customerId": "string",
      "dateCreated": "string",
      "locationId": "string",
      "orderNo": "string",
      "projectedOrder": "string",
      "rmaExpirationDate": "string",
      "ship2Name": "Ava Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `approved` | string |  |
| `completed` | string |  |
| `customerId` | string |  |
| `dateCreated` | string |  |
| `locationId` | string |  |
| `orderNo` | string |  |
| `projectedOrder` | string |  |
| `rmaExpirationDate` | string |  |
| `ship2Name` | string |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /data/erp/views/v1/p21_view_oe_hdr` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-quotes.md) for the provider-specific parameters and requirements.

