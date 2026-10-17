# Alliance HCM: List Employee Status Changes



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-status-changes
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-status-changes?connectionId=$CONNECTION_ID&limit=25&offset=0&companyCode=string&employeeId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "companyCode": "string",
  "employeeId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-status-changes?${params}`, {
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
| `companyCode` | list<string> | yes | Choose the company, or map co from the employee change or paycheck record. |
| `employeeId` | string | yes | Map id from List Employee Changes or Get Employee. Keep the value exactly as returned, including any leading spaces. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "changeDate": "2026-05-07T12:00:00.000Z",
      "changeReason": "string",
      "co": "string",
      "guidfield": "string",
      "id": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastChangeUser": "string",
      "lastDayWorkedDate": "2026-05-07T12:00:00.000Z",
      "newStatus": "string",
      "notes": "string",
      "oldStatus": "string",
      "rehireEligible": true
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `changeDate` | date |  |
| `changeReason` | string |  |
| `co` | string |  |
| `guidfield` | string |  |
| `id` | string |  |
| `lastChange` | date |  |
| `lastChangeUser` | string |  |
| `lastDayWorkedDate` | date |  |
| `newStatus` | string |  |
| `notes` | string |  |
| `oldStatus` | string |  |
| `rehireEligible` | boolean |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-employee-status-changes.md) for the provider-specific parameters and requirements.

