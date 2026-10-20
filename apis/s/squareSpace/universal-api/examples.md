# SquareSpace Universal API Examples

These examples use the MindCloud API key and SquareSpace connection described in [authentication.md](authentication.md). Replace `$CONNECTION_ID` with the connection ID you copied from the Connections page.

## Retrieve Basic Site Information

Retrieves basic site information from Squarespace.

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/squareSpace/latest/actions/retrieve-basic-site-information?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/squareSpace/latest/actions/retrieve-basic-site-information?${params}`, {
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
      "currency": "string",
      "id": "string",
      "language": "string",
      "location": {},
      "measurementStandard": "string",
      "siteId": "string",
      "timeZone": "string",
      "title": "string",
      "url": "https://example.com"
    }
  ],
  "meta": {}
}
```

See the full [Retrieve Basic Site Information action reference](actions/retrieve-basic-site-information.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/squareSpace/latest/actions/retrieve-basic-site-information).

## Adjust Stock Quantities

Updates stock quantities in Squarespace.

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/squareSpace/latest/actions/adjust-stock-quantities" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "idempotencyKey": "string"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/squareSpace/latest/actions/adjust-stock-quantities', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "idempotencyKey": "string"
  })
});

const { success, data } = await response.json();
```

Example response:

```json
{
  "success": true,
  "data": [],
  "meta": {}
}
```

See the full [Adjust Stock Quantities action reference](actions/adjust-stock-quantities.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/squareSpace/latest/actions/adjust-stock-quantities).
