# Alliance HCM: List Employee Pay History



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-history
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-history?connectionId=$CONNECTION_ID&limit=25&offset=0&companyCode=string&employeeId=string" \
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

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-pay-history?${params}`, {
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
      "autoPay": true,
      "batch": "string",
      "beginDate": "2026-05-07T12:00:00.000Z",
      "calendarId": "string",
      "cc": "string",
      "cc1": "string",
      "cc2": "string",
      "cc3": "string",
      "cc4": "string",
      "cc5": "string",
      "checkAttributes": "string",
      "checkDate": "2026-05-07T12:00:00.000Z",
      "checkNumber": 1,
      "checkstubMemo": "string",
      "co": "string",
      "dirDepAmount": 1,
      "documentNumber": 1,
      "endDate": "2026-05-07T12:00:00.000Z",
      "gross": 1,
      "hours": 1,
      "id": "string",
      "inytd": true,
      "isManual": 1,
      "isNocalc": 1,
      "isVoid": 1,
      "jobCode": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastChangeUser": "string",
      "net": 1,
      "netCheck": 1,
      "otDollars": 1,
      "otHours": 1,
      "process": 1,
      "regDollars": 1,
      "regHours": 1,
      "specialCheck": true,
      "trans": "string",
      "userMemo": "string",
      "voidedTrans": "string",
      "voucherNumber": 1,
      "wcc": "string",
      "ww": 1,
      "wwType": 1
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `autoPay` | boolean |  |
| `batch` | string |  |
| `beginDate` | date |  |
| `calendarId` | string |  |
| `cc` | string |  |
| `cc1` | string |  |
| `cc2` | string |  |
| `cc3` | string |  |
| `cc4` | string |  |
| `cc5` | string |  |
| `checkAttributes` | string |  |
| `checkDate` | date |  |
| `checkNumber` | number |  |
| `checkstubMemo` | string |  |
| `co` | string |  |
| `dirDepAmount` | number |  |
| `documentNumber` | number |  |
| `endDate` | date |  |
| `gross` | number |  |
| `hours` | number |  |
| `id` | string |  |
| `inytd` | boolean |  |
| `isManual` | number |  |
| `isNocalc` | number |  |
| `isVoid` | number |  |
| `jobCode` | string |  |
| `lastChange` | date |  |
| `lastChangeUser` | string |  |
| `net` | number |  |
| `netCheck` | number |  |
| `otDollars` | number |  |
| `otHours` | number |  |
| `process` | number |  |
| `regDollars` | number |  |
| `regHours` | number |  |
| `specialCheck` | boolean |  |
| `trans` | string |  |
| `userMemo` | string |  |
| `voidedTrans` | string |  |
| `voucherNumber` | number |  |
| `wcc` | string |  |
| `ww` | number |  |
| `wwType` | number |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-employee-pay-history.md) for the provider-specific parameters and requirements.

