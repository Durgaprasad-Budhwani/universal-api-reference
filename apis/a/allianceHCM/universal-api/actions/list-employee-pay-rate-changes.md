# Alliance HCM: List Employee Pay Rate Changes



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-rate-changes
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-rate-changes?connectionId=$CONNECTION_ID&limit=25&offset=0&companyCode=string&previousCheckpoint=2026-10-01T00%3A00%3A00&currentCheckpoint=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "companyCode": "string",
  "previousCheckpoint": "2026-10-01T00:00:00",
  "currentCheckpoint": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-rate-changes?${params}`, {
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
| `companyCode` | list<string> | yes |  |
| `previousCheckpoint` | string | yes | Return pay-rate changes after this date and time. For your first run, enter when you want to start. For later runs, use the End Date from the last fully completed run. Use Alliance's date/time format, for example 2026-10-01T00:00:00. Example: `2026-10-01T00:00:00`. |
| `currentCheckpoint` | string | yes | Return pay-rate changes up to and including this date and time. Run Get Pay Rate Change Checkpoint for the same company and use its returned date/time exactly as provided. This is the latest time Alliance has finished processing, helping avoid missing delayed changes. After processing all pages, save this value as the next Start Date. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `employeeId` | string | no | Optional. Map id from an employee or change record; leave empty for all employees in the chosen company. |
| `changeType` | list<string> | no | One of: `D`, `I`, `U`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "changeDate": "2026-05-07T12:00:00.000Z",
      "changedBy": "string",
      "changeTable": "string",
      "changeType": "string",
      "co": "string",
      "fieldName": "Ava Chen",
      "guidfield": "string",
      "id": "string",
      "newValue": "string",
      "oldValue": "string",
      "sourceDB": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `changeDate` | date | Time of the change in Alliance's server time. |
| `changedBy` | string |  |
| `changeTable` | string |  |
| `changeType` | string | I = Added, U = Updated, D = Deleted. |
| `co` | string | Company code. Use together with id to identify an employee across companies. |
| `fieldName` | string | The employee or pay-rate field that changed. |
| `guidfield` | string | Unique identifier of the record; in a change log this is the changed record, not a unique change event. |
| `id` | string | Employee ID. Map this value into Employee ID in List Employee Pay Rates. |
| `newValue` | string | New field value, as text. |
| `oldValue` | string | Previous field value, as text. |
| `sourceDB` | string |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-employee-pay-rate-changes.md) for the provider-specific parameters and requirements.

