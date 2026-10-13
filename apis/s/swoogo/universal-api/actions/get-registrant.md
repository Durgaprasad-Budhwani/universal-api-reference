# Swoogo: Get Registrant



```
GET https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/get-registrant
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Swoogo `connectionId` ([setup](../authentication.md)).

## Example request

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

## Inputs

Arguments are sent as query string parameters ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `registrantId` | number | yes |  |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `fields` | string | no |  |
| `expand` | string | no | Comma-separated related objects: homeAddress, workAddress, billingAddress. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native Swoogo API returns.

## Native endpoint

Through the native Swoogo API, this operation is `GET /registrants/:registrant_id` (base URL `https://api.swoogo.com/api/v1`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-registrant.md) for the provider-specific parameters and requirements.

