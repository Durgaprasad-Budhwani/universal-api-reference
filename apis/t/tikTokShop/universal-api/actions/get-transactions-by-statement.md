# TikTok Shop: Get Transactions by Statement



```
GET https://connect.mindcloud.co/v1/universal/tikTokShop/latest/actions/get-transactions-by-statement
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a TikTok Shop `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/tikTokShop/latest/actions/get-transactions-by-statement?connectionId=$CONNECTION_ID&limit=25&offset=0&statement_id=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "statement_id": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/tikTokShop/latest/actions/get-transactions-by-statement?${params}`, {
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
| `shop_cipher` | string | no |  |
| `statement_id` | string | yes |  |
| `sort_field` | string | no | Default: `order_create_time`. |
| `version` | string | no | Default: `202501`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": "string",
      "createTime": 1,
      "currency": "string",
      "status": "string",
      "payableAmount": "string",
      "totalReserveAmount": "string",
      "totalSettlementAmount": "string",
      "totalSettlementBreakdown": {},
      "transactions": [
        {}
      ]
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | string |  |
| `createTime` | number |  |
| `currency` | string |  |
| `status` | string |  |
| `payableAmount` | string |  |
| `totalReserveAmount` | string |  |
| `totalSettlementAmount` | string |  |
| `totalSettlementBreakdown` | object |  |
| `transactions` | array<object> |  |

## Native endpoint

Through the native TikTok Shop API, this operation is `GET finance/:version/statements/:statement_id/statement_transactions` (base URL `https://open-api.tiktokglobalshop.com/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/get-transactions-by-statement.md) for the provider-specific parameters and requirements.

