# Swoogo: List Events



```
GET https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/list-events
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Swoogo `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`), [sorting](../sorting.md) (`sort`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/list-events?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/list-events?${params}`, {
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
| `search` | string | no | Swoogo search conditions, for example status=live or name=*conference*. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `ids` | number | no | Retrieve only these positive event IDs; maximum 100 IDs. Accepts multiple values in one string, delimited by `,`. |
| `fields` | string | no | Fields to return. If omitted, Swoogo returns event ID and name. Accepts multiple values in one string, delimited by `,`. |
| `expand` | list<string> | no | Include the event folder or location. One of: `folder`, `location`. Accepts multiple values in one string, delimited by `,`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Ava Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | number |  |
| `name` | string |  |

## Native endpoint

Through the native Swoogo API, this operation is `GET /events` (base URL `https://api.swoogo.com/api/v1`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-events.md) for the provider-specific parameters and requirements.

