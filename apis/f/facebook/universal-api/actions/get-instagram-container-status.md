# Facebook: Get Instagram Container Status



```
GET https://connect.mindcloud.co/v1/universal/facebook/latest/actions/get-instagram-container-status
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Facebook `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/facebook/latest/actions/get-instagram-container-status?connectionId=$CONNECTION_ID&containerId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "containerId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/facebook/latest/actions/get-instagram-container-status?${params}`, {
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
| `containerId` | string | yes |  |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `fields` | list<string> | no | One of: `copyright_check_status`, `id`, `status`, `status_code`. Accepts multiple values in one string, delimited by `,`. Default: `id,status_code,status`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": "string",
      "status": "string",
      "statusCode": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | string |  |
| `status` | string |  |
| `statusCode` | string |  |

## Native endpoint

Through the native Facebook API, this operation is `GET https://graph.facebook.com/v26.0/:containerId` (base URL `https://graph.facebook.com/v25.0`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-instagram-container-status.md) for the provider-specific parameters and requirements.

