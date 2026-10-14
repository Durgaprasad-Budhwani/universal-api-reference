# Facebook: Get Instagram Publishing Limit



```
GET https://connect.mindcloud.co/v1/universal/facebook/latest/actions/get-instagram-publishing-limit
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Facebook `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/facebook/latest/actions/get-instagram-publishing-limit?connectionId=$CONNECTION_ID&instagramAccountId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "instagramAccountId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/facebook/latest/actions/get-instagram-publishing-limit?${params}`, {
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
| `instagramAccountId` | string | yes | Professional Instagram account ID linked to your Facebook Page. Use Get Page with instagram_business_account to discover it. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `fields` | list<string> | no | One of: `config`, `quota_usage`. Accepts multiple values in one string, delimited by `,`. Default: `quota_usage,config`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "config": {
        "quotaDuration": 1,
        "quotaTotal": 1
      },
      "quotaUsage": 1
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `config` | object |  |
| `config.quotaDuration` | number |  |
| `config.quotaTotal` | number |  |
| `quotaUsage` | number |  |

## Native endpoint

Through the native Facebook API, this operation is `GET https://graph.facebook.com/v26.0/:instagramAccountId/content_publishing_limit` (base URL `https://graph.facebook.com/v25.0`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-instagram-publishing-limit.md) for the provider-specific parameters and requirements.

