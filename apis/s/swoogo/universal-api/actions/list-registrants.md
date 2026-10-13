# Swoogo: List Registrants



```
GET https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/list-registrants
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Swoogo `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`), [sorting](../sorting.md) (`sort`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/list-registrants?connectionId=$CONNECTION_ID&limit=25&offset=0&eventId=1" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "eventId": "1"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/list-registrants?${params}`, {
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
| `eventId` | list<number> | yes | The event whose registrants you want to list. |
| `search` | string | no | Swoogo search conditions, for example registration_status=confirmed or email=*@example.com*. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `ids` | number | no | Retrieve only these positive registrant IDs; maximum 100 IDs. Accepts multiple values in one string, delimited by `,`. |
| `fields` | string | no | Fields to return. If omitted, Swoogo returns ID, first name, and last name. Accepts multiple values in one string, delimited by `,`. |
| `expand` | list<string> | no | Include related address objects. One of: `billingAddress`, `homeAddress`, `workAddress`. Accepts multiple values in one string, delimited by `,`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "firstName": "Ava",
      "id": 1,
      "lastName": "Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `firstName` | string |  |
| `id` | number |  |
| `lastName` | string |  |

## Native endpoint

Through the native Swoogo API, this operation is `GET /registrants` (base URL `https://api.swoogo.com/api/v1`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-registrants.md) for the provider-specific parameters and requirements.

