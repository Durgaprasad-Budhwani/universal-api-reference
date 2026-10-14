# Epicor Prophet 21 Universal API Examples

These examples use the MindCloud API key and Epicor Prophet 21 connection described in [authentication.md](authentication.md). Replace `$CONNECTION_ID` with the connection ID you copied from the Connections page.

## List Product Groups



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

Example response:

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

See the full [List Product Groups action reference](actions/list-product-groups.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/epicorProphet21/latest/actions/list-product-groups).
