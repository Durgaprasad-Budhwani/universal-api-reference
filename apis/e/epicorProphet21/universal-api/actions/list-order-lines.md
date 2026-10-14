# Epicor Prophet 21: List Order Lines



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-order-lines
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-order-lines?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-order-lines?${params}`, {
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
| `select` | string | no | Comma-separated field names. Leave empty to return all available fields. Default: `product_group_id,extended_price,item_id,oe_line_uid,qty_ordered,unit_price,order_no`. |
| `filter` | string | no | A Prophet 21 filter expression, such as customer_id eq 123. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "extendedPrice": "string",
      "itemId": "string",
      "oeLineUid": 1,
      "orderNo": "string",
      "productGroupId": "string",
      "qtyOrdered": "string",
      "unitPrice": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `extendedPrice` | string |  |
| `itemId` | string |  |
| `oeLineUid` | number |  |
| `orderNo` | string |  |
| `productGroupId` | string |  |
| `qtyOrdered` | string |  |
| `unitPrice` | string |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /data/erp/views/v1/p21_view_oe_line` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-order-lines.md) for the provider-specific parameters and requirements.

