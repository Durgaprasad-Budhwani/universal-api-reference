# Epicor Prophet 21: List Customers



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-customers
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-customers?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-customers?${params}`, {
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
| `select` | string | no | Default: `customer_id,salesrep_id,customer_name`. |
| `filter` | string | no | Default: `delete_flag eq 'N'`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "customerId": "string",
      "customerName": "Ava Chen",
      "salesrepId": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `customerId` | string |  |
| `customerName` | string |  |
| `salesrepId` | string |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /data/erp/views/v1/p21_view_customer` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-customers.md) for the provider-specific parameters and requirements.

