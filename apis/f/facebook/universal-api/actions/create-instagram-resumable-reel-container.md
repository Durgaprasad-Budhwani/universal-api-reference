# Facebook: Create Instagram Resumable Reel Container



```
POST https://connect.mindcloud.co/v1/universal/facebook/latest/actions/create-instagram-resumable-reel-container
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Facebook `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/facebook/latest/actions/create-instagram-resumable-reel-container" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "instagramAccountId": "string"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/facebook/latest/actions/create-instagram-resumable-reel-container', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "instagramAccountId": "string"
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `instagramAccountId` | string | yes |  |
| `caption` | string | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": "string",
      "uri": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | string |  |
| `uri` | string |  |

## Native endpoint

Through the native Facebook API, this operation is `POST https://graph.facebook.com/v26.0/:instagramAccountId/media` (base URL `https://graph.facebook.com/v25.0`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/create-instagram-resumable-reel-container.md) for the provider-specific parameters and requirements.

