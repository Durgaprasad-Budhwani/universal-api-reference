# Alliance HCM Universal API Examples

These examples use the MindCloud API key and Alliance HCM connection described in [authentication.md](authentication.md). Replace `$CONNECTION_ID` with the connection ID you copied from the Connections page.

## Get Database Time



```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-database-time?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-database-time?${params}`, {
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
      "response": "string"
    }
  ],
  "meta": {}
}
```

See the full [Get Database Time action reference](actions/get-database-time.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/allianceHCM/latest/actions/get-database-time).
