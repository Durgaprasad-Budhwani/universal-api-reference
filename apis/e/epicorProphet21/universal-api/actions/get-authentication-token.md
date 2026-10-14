# Epicor Prophet 21: Get Authentication Token



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/get-authentication-token
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/get-authentication-token?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/get-authentication-token?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```



## Response

```json
{
  "success": true,
  "data": [
    {
      "accessToken": "string",
      "expiresIn": 1,
      "refreshToken": "string",
      "scope": "string",
      "sessionId": "string",
      "tokenType": "string",
      "userName": "Ava Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `accessToken` | string |  |
| `expiresIn` | number |  |
| `refreshToken` | string |  |
| `scope` | string |  |
| `sessionId` | string |  |
| `tokenType` | string |  |
| `userName` | string |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `POST /api/security/token/` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-authentication-token.md) for the provider-specific parameters and requirements.

