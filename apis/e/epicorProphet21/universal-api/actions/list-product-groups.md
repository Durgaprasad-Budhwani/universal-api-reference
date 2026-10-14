# Epicor Prophet 21: List Product Groups



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-product-groups
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-product-groups?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-product-groups?${params}`, {
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
| `select` | string | no | Comma-separated field names. Leave empty to return all available fields. |
| `filter` | string | no | A Prophet 21 filter expression, such as customer_id eq 123. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "adminFeeFlag": "string",
      "applyMinMarginRulesFlag": "string",
      "assetAccountNo": "string",
      "companyId": "string",
      "compressorFlag": "string",
      "cosAccountNo": "string",
      "dateCreated": "string",
      "dateLastModified": "string",
      "deleteFlag": "string",
      "enableLineProfitWarning": "string",
      "environmentalFeeFlag": "string",
      "includeInSizeAnalysisFlag": "string",
      "lastMaintainedBy": "string",
      "oeSkipProfitCheckUncosted": "string",
      "oeSkipProfitCheckUnpriced": "string",
      "priceRoundingFlag": "string",
      "productGroupDesc": "string",
      "productGroupId": "string",
      "productGroupUid": 1,
      "revenueAccountNo": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `adminFeeFlag` | string |  |
| `applyMinMarginRulesFlag` | string |  |
| `assetAccountNo` | string |  |
| `companyId` | string |  |
| `compressorFlag` | string |  |
| `cosAccountNo` | string |  |
| `dateCreated` | string |  |
| `dateLastModified` | string |  |
| `deleteFlag` | string |  |
| `enableLineProfitWarning` | string |  |
| `environmentalFeeFlag` | string |  |
| `includeInSizeAnalysisFlag` | string |  |
| `lastMaintainedBy` | string |  |
| `oeSkipProfitCheckUncosted` | string |  |
| `oeSkipProfitCheckUnpriced` | string |  |
| `priceRoundingFlag` | string |  |
| `productGroupDesc` | string |  |
| `productGroupId` | string |  |
| `productGroupUid` | number |  |
| `revenueAccountNo` | string |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /data/erp/views/v1/p21_view_product_group` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-product-groups.md) for the provider-specific parameters and requirements.

