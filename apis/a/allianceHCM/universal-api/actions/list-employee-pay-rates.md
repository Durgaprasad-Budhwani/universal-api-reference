# Alliance HCM: List Employee Pay Rates



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-rates
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-rates?connectionId=$CONNECTION_ID&limit=25&offset=0&companyCode=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "companyCode": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-rates?${params}`, {
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
| `employeeId` | string | no | Optional. Use id from an employee or change record. Leave empty to list rates for all employees in the chosen company. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `rateCode` | string | no | Optional. Enter a known rate code such as Base, or leave empty to include every pay rate. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "cc1": "string",
      "cc2": "string",
      "cc3": "string",
      "cc4": "string",
      "cc5": "string",
      "changeReason": "string",
      "co": "string",
      "effectiveDate": "2026-05-07T12:00:00.000Z",
      "endDate": "2026-05-07T12:00:00.000Z",
      "guidfield": "string",
      "id": "string",
      "jobCode": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastChangeUser": "string",
      "notes": "string",
      "paygrade": "string",
      "rate": 1,
      "rateCode": "string",
      "ratePer": "string",
      "salary": 1,
      "shift": "string",
      "startDate": "2026-05-07T12:00:00.000Z"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `cc1` | string |  |
| `cc2` | string |  |
| `cc3` | string |  |
| `cc4` | string |  |
| `cc5` | string |  |
| `changeReason` | string |  |
| `co` | string |  |
| `effectiveDate` | date |  |
| `endDate` | date |  |
| `guidfield` | string |  |
| `id` | string |  |
| `jobCode` | string |  |
| `lastChange` | date |  |
| `lastChangeUser` | string |  |
| `notes` | string |  |
| `paygrade` | string |  |
| `rate` | number |  |
| `rateCode` | string |  |
| `ratePer` | string |  |
| `salary` | number |  |
| `shift` | string |  |
| `startDate` | date |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-employee-pay-rates.md) for the provider-specific parameters and requirements.

