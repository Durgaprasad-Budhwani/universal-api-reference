# Alliance HCM: List Employee Job Changes



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-job-changes
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-job-changes?connectionId=$CONNECTION_ID&limit=25&offset=0&companyCode=string&employeeId=string" \
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

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-job-changes?${params}`, {
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
| `companyCode` | list<string> | yes | Choose the company, or map co from List Employee Changes. |
| `employeeId` | string | yes | Map id from List Employee Changes or Get Employee. Use the value exactly as returned, including any leading spaces. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "changeDate": "2026-05-07T12:00:00.000Z",
      "co": "string",
      "guidfield": "string",
      "id": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastChangeUser": "string",
      "newcc1": "string",
      "newcc2": "string",
      "newcc3": "string",
      "newcc4": "string",
      "newcc5": "string",
      "neweeoclass": "string",
      "newFLSAOtExempt": true,
      "newpositioncode": "string",
      "newSocCode": "string",
      "newSupervisorId": "string",
      "newtitle": "string",
      "newWcc": "string",
      "notes": "string",
      "oldcc1": "string",
      "oldcc2": "string",
      "oldcc3": "string",
      "oldcc4": "string",
      "oldcc5": "string",
      "oldeeoclass": "string",
      "oldFLSAOtExempt": true,
      "oldpositioncode": "string",
      "oldSocCode": "string",
      "oldSupervisorId": "string",
      "oldtitle": "string",
      "oldWcc": "string",
      "reason": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `changeDate` | date |  |
| `co` | string |  |
| `guidfield` | string |  |
| `id` | string |  |
| `lastChange` | date |  |
| `lastChangeUser` | string |  |
| `newcc1` | string |  |
| `newcc2` | string |  |
| `newcc3` | string |  |
| `newcc4` | string |  |
| `newcc5` | string |  |
| `neweeoclass` | string |  |
| `newFLSAOtExempt` | boolean |  |
| `newpositioncode` | string |  |
| `newSocCode` | string |  |
| `newSupervisorId` | string |  |
| `newtitle` | string |  |
| `newWcc` | string |  |
| `notes` | string |  |
| `oldcc1` | string |  |
| `oldcc2` | string |  |
| `oldcc3` | string |  |
| `oldcc4` | string |  |
| `oldcc5` | string |  |
| `oldeeoclass` | string |  |
| `oldFLSAOtExempt` | boolean |  |
| `oldpositioncode` | string |  |
| `oldSocCode` | string |  |
| `oldSupervisorId` | string |  |
| `oldtitle` | string |  |
| `oldWcc` | string |  |
| `reason` | string |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-employee-job-changes.md) for the provider-specific parameters and requirements.

