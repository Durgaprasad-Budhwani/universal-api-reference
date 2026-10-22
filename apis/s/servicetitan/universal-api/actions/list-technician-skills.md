# ServiceTitan: List Technician Skills



```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-technician-skills
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-technician-skills?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-technician-skills?${params}`, {
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
| `technicianId` | number | no | The technician whose skills to return. Use Get Technicians to find the technician ID. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `includeTotal` | boolean | no | Include the total number of matching technician skills. |
| `active` | list<string> | no | Choose active skills, inactive skills, or both. Only active skills are returned when left empty. One of: `Any`, `False`, `True`. |
| `createdBefore` | date | no | Return skills created before this date and time in UTC. Example: `2026-01-15T10:30:00Z`. |
| `createdOnOrAfter` | date | no | Return skills created on or after this date and time in UTC. Example: `2026-01-15T10:30:00Z`. |
| `modifiedBefore` | date | no | Return skills modified before this date and time in UTC. Example: `2026-01-15T10:30:00Z`. |
| `modifiedOnOrAfter` | date | no | Return skills modified on or after this date and time in UTC. Example: `2026-01-15T10:30:00Z`. |
| `sort` | string | no | Sort by Id, CreatedOn, or ModifiedOn. Use + for ascending order or - for descending order, for example -ModifiedOn. Example: `-ModifiedOn`. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native ServiceTitan API returns.

## Native endpoint

Through the native ServiceTitan API, this operation is `GET dispatch/v2/tenant/{{credentials.tenant}}/technician-skills` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-technician-skills.md) for the provider-specific parameters and requirements.

