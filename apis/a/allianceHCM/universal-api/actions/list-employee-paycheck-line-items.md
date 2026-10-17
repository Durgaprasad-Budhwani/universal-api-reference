# Alliance HCM: List Employee Paycheck Line Items



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-paycheck-line-items
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-paycheck-line-items?connectionId=$CONNECTION_ID&limit=25&offset=0&companyCode=string&paycheckTransactionId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "companyCode": "string",
  "paycheckTransactionId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-employee-paycheck-line-items?${params}`, {
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
| `paycheckTransactionId` | string | yes | Map trans from List Employee Pay History. This identifies one processed paycheck. Retrieve pay history using the Employee ID first. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "amount": 1,
      "beginDate": "2026-05-07T12:00:00.000Z",
      "cc1": "string",
      "cc2": "string",
      "cc3": "string",
      "cc4": "string",
      "cc5": "string",
      "co": "string",
      "comment": "string",
      "det": "string",
      "detCode": "string",
      "endDate": "2026-05-07T12:00:00.000Z",
      "guidfield": "string",
      "hours": 1,
      "jobCode": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastChangeUser": "string",
      "rate": 1,
      "rateCode": "string",
      "shift": "string",
      "subTrans": 1,
      "trans": "string",
      "transType": "string",
      "wcc": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `amount` | number |  |
| `beginDate` | date |  |
| `cc1` | string |  |
| `cc2` | string |  |
| `cc3` | string |  |
| `cc4` | string |  |
| `cc5` | string |  |
| `co` | string |  |
| `comment` | string |  |
| `det` | string |  |
| `detCode` | string |  |
| `endDate` | date |  |
| `guidfield` | string |  |
| `hours` | number |  |
| `jobCode` | string |  |
| `lastChange` | date |  |
| `lastChangeUser` | string |  |
| `rate` | number |  |
| `rateCode` | string |  |
| `shift` | string |  |
| `subTrans` | number |  |
| `trans` | string |  |
| `transType` | string |  |
| `wcc` | string |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-employee-paycheck-line-items.md) for the provider-specific parameters and requirements.

