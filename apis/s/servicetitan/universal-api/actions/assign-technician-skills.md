# ServiceTitan: Assign Technician Skills



```
PUT https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/assign-technician-skills
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/assign-technician-skills" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "technicianId": 1,
  "skillIds[]": [
    1
  ],
  "replaceExistingSkills": true
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/assign-technician-skills', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "technicianId": 1,
    "skillIds[]": [1],
    "replaceExistingSkills": true
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `technicianId` | number | yes | The technician to assign existing skills to. Use Get Technicians to find the technician ID. |
| `skillIds[]` | array<number> | yes | The numeric IDs of the existing skills to assign to the technician. |
| `replaceExistingSkills` | boolean | yes | True replaces all of the technician's current skills and removes skills not in this list. False adds these skills while keeping the technician's current skills. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "technicianSkills": [
        [
          {}
        ]
      ],
      "updated": true
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `technicianSkills[]` | array<object> | All technician skills after the change. |
| `technicianSkills[].active` | boolean | Whether the skill is active. |
| `technicianSkills[].createdOn` | date | Date and time the skill was created, in UTC. |
| `technicianSkills[].id` | string | Technician skill ID in {TechnicianId}_{SkillId} format. |
| `technicianSkills[].jobTypeIds[]` | array<number> | Job type IDs for this skill. May be null. |
| `technicianSkills[].modifiedOn` | date | Date and time the skill was last modified, in UTC. |
| `technicianSkills[].name` | string | Name of the skill. |
| `technicianSkills[].technicianId` | number | ID of the technician assigned this skill. |
| `updated` | boolean | Whether the update succeeded. |

## Native endpoint

Through the native ServiceTitan API, this operation is `PATCH dispatch/v2/tenant/{{credentials.tenant}}/technician-skills` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/assign-technician-skills.md) for the provider-specific parameters and requirements.

