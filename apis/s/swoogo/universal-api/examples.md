# Swoogo Universal API Examples

These examples use the MindCloud API key and Swoogo connection described in [authentication.md](authentication.md). Replace `$CONNECTION_ID` with the connection ID you copied from the Connections page.

## Get Registrant



```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/get-registrant?connectionId=$CONNECTION_ID&registrantId=1" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "registrantId": "1"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/get-registrant?${params}`, {
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
  "data": [],
  "meta": {}
}
```

See the full [Get Registrant action reference](actions/get-registrant.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/swoogo/latest/actions/get-registrant).
