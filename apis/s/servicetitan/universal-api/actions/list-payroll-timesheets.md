# ServiceTitan: List Payroll Timesheets

Retrieves payroll job timesheets from ServiceTitan.

```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-payroll-timesheets
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-payroll-timesheets?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-payroll-timesheets?${params}`, {
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
| `technicianId` | number | no |  |
| `active` | list | no | One of: `Any`, `False`, `True`. Default: `Any`. |
| `pageSize` | number | no | Default: `500`. |
| `modifiedOnOrAfter` | string | no |  |
| `endedOn` | string | no |  |
| `jobIds` | string | no |  |
| `startedOn` | string | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "jobId": 1,
      "appointmentId": 1,
      "technicianId": 1,
      "dispatchedOn": "string",
      "arrivedOn": "string",
      "doneOn": "string",
      "canceledOn": "string",
      "active": true,
      "createdOn": "string",
      "modifiedOn": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | number | Timesheet ID. |
| `jobId` | number | ID of the associated job. |
| `appointmentId` | number | ID of the associated appointment. |
| `technicianId` | number | ID of the technician. |
| `dispatchedOn` | string | Timestamp when the technician was dispatched. |
| `arrivedOn` | string | Timestamp when the technician arrived. |
| `doneOn` | string | Timestamp when the work was completed. |
| `canceledOn` | string | Timestamp when the timesheet was canceled. |
| `active` | boolean | Whether the timesheet is active. |
| `createdOn` | string | Timestamp when the timesheet was created. |
| `modifiedOn` | string | Timestamp when the timesheet was last modified. |

## Native endpoint

Through the native ServiceTitan API, this operation is `GET payroll/v2/tenant/{{credentials.tenant}}/jobs/timesheets` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-payroll-timesheets.md) for the provider-specific parameters and requirements.

