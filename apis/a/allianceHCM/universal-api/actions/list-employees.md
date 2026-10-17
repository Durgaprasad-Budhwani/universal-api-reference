# Alliance HCM: List Employees



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employees
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employees?connectionId=$CONNECTION_ID&limit=25&offset=0&companyCode=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "companyCode": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employees?${params}`, {
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

## Response

```json
{
  "success": true,
  "data": [
    {
      "co": "string",
      "empStatus": "string",
      "firstName": "Ava",
      "guidfield": "string",
      "id": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastName": "Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `co` | string | Company code. Use together with id to identify an employee across companies. |
| `empStatus` | string |  |
| `firstName` | string |  |
| `guidfield` | string | Unique identifier of the record; in a change log this is the changed record, not a unique change event. |
| `id` | string | Employee ID. Map this value into Employee ID in List Employee Pay Rates. |
| `lastChange` | date |  |
| `lastName` | string |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-employees.md) for the provider-specific parameters and requirements.

