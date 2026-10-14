# X: Append Media Upload



```
PUT https://connect.mindcloud.co/v1/universal/x/latest/actions/append-media-upload
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a X `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/x/latest/actions/append-media-upload" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "id": "string",
  "media": "string",
  "segmentIndex": 1
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/x/latest/actions/append-media-upload', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "id": "string",
    "media": "string",
    "segmentIndex": 1
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | string | yes | Media ID returned by Initialize Media Upload. |
| `media` | string | yes | Base64-encoded chunk contents for JSON upload. |
| `segmentIndex` | number | yes | Zero-based chunk index, 0–9999. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native X API returns.

## Native endpoint

Through the native X API, this operation is `POST /2/media/upload/:id/append` (base URL `https://api.x.com`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/append-media-upload.md) for the provider-specific parameters and requirements.

