# ServiceTitan: Get Job Types



```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-job-types
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-job-types?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-job-types?${params}`, {
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
| `active` | string | no | What kind of items should be returned (only active items will be returned by default) |
| `ids` | string | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "active": true,
      "businessUnitIds": [
        1
      ],
      "class": "string",
      "createdOn": "string",
      "customFieldTypeIds": [
        1
      ],
      "defaultEstimateSoldAction": "string",
      "duration": 1,
      "enforceRecurringServiceEventSelection": true,
      "externalData": {},
      "id": 1,
      "invoiceSignaturesRequired": true,
      "isSmartDispatched": true,
      "modifiedOn": "string",
      "name": "Ava Chen",
      "noCharge": true,
      "priority": "string",
      "skills": [
        1
      ],
      "soldThreshold": 1,
      "summary": "string",
      "tagTypeIds": [
        1
      ]
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `active` | boolean | Whether the job type is active. |
| `businessUnitIds` | array<number> | Business unit IDs associated with the job type. |
| `class` | string | Job type class. |
| `createdOn` | string | Timestamp when the job type was created. |
| `customFieldTypeIds` | array<number> | Custom field type IDs associated with the job type. |
| `defaultEstimateSoldAction` | string | Default estimate sold action. |
| `duration` | number | Default duration in seconds. |
| `enforceRecurringServiceEventSelection` | boolean | Whether recurring service event selection is enforced. |
| `externalData` | object | External data associated with the job type. |
| `id` | number | Job type ID. |
| `invoiceSignaturesRequired` | boolean | Whether invoice signatures are required. |
| `isSmartDispatched` | boolean | Whether the job type is smart dispatched. |
| `modifiedOn` | string | Timestamp when the job type was last modified. |
| `name` | string | Job type name. |
| `noCharge` | boolean | Whether the job type is no charge. |
| `priority` | string | Priority of the job type. |
| `skills` | array<number> | Skills associated with the job type. |
| `soldThreshold` | number | Sold threshold value. |
| `summary` | string | Job type summary. |
| `tagTypeIds` | array<number> | Tag type IDs associated with the job type. |

## Native endpoint

Through the native ServiceTitan API, this operation is `GET https://api.servicetitan.io/jpm/v2/tenant/{{credentials.tenant}}/job-types` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/get-job-types.md) for the provider-specific parameters and requirements.

