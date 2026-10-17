# Alliance HCM: Get Employee Employment Details



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-employee-employment-details
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-employee-employment-details?connectionId=$CONNECTION_ID&companyCode=string&employeeId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "companyCode": "string",
  "employeeId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-employee-employment-details?${params}`, {
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
      "co": "string",
      "desiredHours": 1,
      "employmentNote": "string",
      "geid": "string",
      "guidfield": "string",
      "id": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastChangeUser": "string",
      "lastDayWorked": "2026-05-07T12:00:00.000Z",
      "preferredLanguage": "string",
      "rehireEligible": true,
      "retirementDate": "2026-05-07T12:00:00.000Z",
      "timeSheet": "string",
      "workArrangement": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `co` | string |  |
| `desiredHours` | number |  |
| `employmentNote` | string |  |
| `geid` | string |  |
| `guidfield` | string |  |
| `id` | string |  |
| `lastChange` | date |  |
| `lastChangeUser` | string |  |
| `lastDayWorked` | date |  |
| `preferredLanguage` | string |  |
| `rehireEligible` | boolean |  |
| `retirementDate` | date |  |
| `timeSheet` | string |  |
| `workArrangement` | string |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-employee-employment-details.md) for the provider-specific parameters and requirements.

