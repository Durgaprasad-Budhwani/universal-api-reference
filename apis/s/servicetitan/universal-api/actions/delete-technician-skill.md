# ServiceTitan: Delete Technician Skill



```
DELETE https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/delete-technician-skill
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X DELETE "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/delete-technician-skill?connectionId=$CONNECTION_ID&id=12345_67890" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "id": "12345_67890"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/delete-technician-skill?${params}`, {
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
| `id` | string | yes | The technician skill ID, formatted {TechnicianId}_{SkillId}, as returned by List Technician Skills. Example: `12345_67890`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | string | ID of the technician skill association removed. |

## Native endpoint

Through the native ServiceTitan API, this operation is `DELETE dispatch/v2/tenant/{{credentials.tenant}}/technician-skills/:id` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/delete-technician-skill.md) for the provider-specific parameters and requirements.

