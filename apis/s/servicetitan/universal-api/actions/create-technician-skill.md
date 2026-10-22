# ServiceTitan: Create Technician Skill



```
POST https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/create-technician-skill
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/create-technician-skill" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "technicianId": 1,
  "name": "Ava Chen",
  "active": true
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/create-technician-skill', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "technicianId": 1,
    "name": "Ava Chen",
    "active": true
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `technicianId` | number | yes | The technician to assign the new skill to. Use Get Technicians to find the technician ID. |
| `name` | string | yes | The name of the new skill. |
| `active` | boolean | yes | Whether the new skill is active. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "active": true,
      "createdOn": "2026-05-07T12:00:00.000Z",
      "id": "string",
      "jobTypeIds": [
        [
          1
        ]
      ],
      "modifiedOn": "2026-05-07T12:00:00.000Z",
      "name": "Ava Chen",
      "technicianId": 1
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `active` | boolean | Whether the skill is active. |
| `createdOn` | date | Date and time the skill was created, in UTC. |
| `id` | string | Technician skill ID in {TechnicianId}_{SkillId} format. |
| `jobTypeIds[]` | array<number> | Job type IDs for this skill. May be null. |
| `modifiedOn` | date | Date and time the skill was last modified, in UTC. |
| `name` | string | Name of the skill. |
| `technicianId` | number | ID of the technician assigned this skill. |

## Native endpoint

Through the native ServiceTitan API, this operation is `POST dispatch/v2/tenant/{{credentials.tenant}}/technician-skills` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/create-technician-skill.md) for the provider-specific parameters and requirements.

