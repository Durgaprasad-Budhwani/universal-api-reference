# Facebook Universal API Examples

These examples use the MindCloud API key and Facebook connection described in [authentication.md](authentication.md). Replace `$CONNECTION_ID` with the connection ID you copied from the Connections page.

## List Pages

List pages you manage/own

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/facebook/latest/actions/list-pages?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/facebook/latest/actions/list-pages?${params}`, {
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
      "category": "string",
      "id": "string",
      "name": "Ava Chen",
      "tasks": [
        "string"
      ]
    }
  ],
  "meta": {}
}
```

See the full [List Pages action reference](actions/list-pages.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/facebook/latest/actions/list-pages).

## Create Instagram Carousel Container



```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/facebook/latest/actions/create-instagram-carousel-container" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "instagramAccountId": "string",
  "children": "string"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/facebook/latest/actions/create-instagram-carousel-container', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "instagramAccountId": "string",
    "children": "string"
  })
});

const { success, data } = await response.json();
```

Example response:

```json
{
  "success": true,
  "data": [
    {
      "id": "string"
    }
  ],
  "meta": {}
}
```

See the full [Create Instagram Carousel Container action reference](actions/create-instagram-carousel-container.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/facebook/latest/actions/create-instagram-carousel-container).
