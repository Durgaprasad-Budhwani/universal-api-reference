# Aspire: List Object Codes

Retrieve a list of information related to object codes.

```
GET https://connect.mindcloud.co/v1/universal/aspire/latest/actions/list-object-codes
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Aspire `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/aspire/latest/actions/list-object-codes?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/aspire/latest/actions/list-object-codes?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```



## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native Aspire API returns.

## Native endpoint

Through the native Aspire API, this operation is `GET ObjectCodes` (base URL `https://{{credentials.environment}}.youraspire.com/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-object-codes.md) for the provider-specific parameters and requirements.

