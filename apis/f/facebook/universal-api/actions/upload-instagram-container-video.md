# Facebook: Upload Instagram Container Video



```
POST https://connect.mindcloud.co/v1/universal/facebook/latest/actions/upload-instagram-container-video
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Facebook `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/facebook/latest/actions/upload-instagram-container-video" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "containerId": "string",
  "video": "string"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/facebook/latest/actions/upload-instagram-container-video', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "containerId": "string",
    "video": "string"
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `containerId` | string | yes |  |
| `video` | file | yes |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "message": "string",
      "success": true
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `message` | string |  |
| `success` | boolean |  |

## Native endpoint

Through the native Facebook API, this operation is `POST https://rupload.facebook.com/ig-api-upload/v26.0/:containerId` (base URL `https://graph.facebook.com/v25.0`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/upload-instagram-container-video.md) for the provider-specific parameters and requirements.

