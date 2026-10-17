# Alliance HCM: Get Employee



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-employee
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-employee?connectionId=$CONNECTION_ID&companyCode=string&employeeId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "companyCode": "string",
  "employeeId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-employee?${params}`, {
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
| `companyCode` | list<string> | yes | Choose the company, or map co from List Employee Changes. Employee IDs are specific to a company. |
| `employeeId` | string | yes | Map id from List Employee Changes or List Employees. Use the value exactly as returned, including any leading spaces. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "address1": "string",
      "address2": "string",
      "adjSeniorityDate": "2026-05-07T12:00:00.000Z",
      "autoPay": "string",
      "cc1": "string",
      "cc2": "string",
      "cc3": "string",
      "cc4": "string",
      "cc5": "string",
      "cellPhone": "string",
      "city": "string",
      "clock": "string",
      "co": "string",
      "country": "string",
      "county": "string",
      "defaultHours": 1,
      "distributionCodes": "string",
      "eeoClass": "string",
      "emailAddress": "ava@example.com",
      "empStatus": "string",
      "empType": "string",
      "firstName": "Ava",
      "flsaOTExempt": true,
      "guidfield": "string",
      "hireDate": "2026-05-07T12:00:00.000Z",
      "homePhone": "string",
      "id": "string",
      "jobCode": "string",
      "lastChange": "2026-05-07T12:00:00.000Z",
      "lastChangeUser": "string",
      "lastName": "Chen",
      "lastRaiseAmount": 1,
      "lastRaiseDate": "2026-05-07T12:00:00.000Z",
      "lastRaiseReason": "string",
      "lastReviewDate": "2026-05-07T12:00:00.000Z",
      "lastReviewRating": "string",
      "mailStop": "string",
      "middleName": "Ava Chen",
      "nextRaiseDate": "2026-05-07T12:00:00.000Z",
      "nextReviewDate": "2026-05-07T12:00:00.000Z",
      "nickname": "Ava Chen",
      "payFrequency": "string",
      "payGrade": "string",
      "payGroup": "string",
      "positionCode": "string",
      "positionInfoLocked": true,
      "priorLastName": "Chen",
      "probation": true,
      "ratePer": "string",
      "rehireDate": "2026-05-07T12:00:00.000Z",
      "salutation": "string",
      "seasonal": true,
      "soc": "string",
      "state": "string",
      "supervisorID": "string",
      "supervisorName": "Ava Chen",
      "surname": "Ava Chen",
      "termDate": "2026-05-07T12:00:00.000Z",
      "termReason": "string",
      "tipped": "string",
      "title": "string",
      "user7": "string",
      "wageType": "string",
      "wcc": "string",
      "workPhone": "string",
      "workPhoneExt": "string",
      "workState": "string",
      "zip": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `address1` | string |  |
| `address2` | string |  |
| `adjSeniorityDate` | date |  |
| `autoPay` | string |  |
| `cc1` | string |  |
| `cc2` | string |  |
| `cc3` | string |  |
| `cc4` | string |  |
| `cc5` | string |  |
| `cellPhone` | string |  |
| `city` | string |  |
| `clock` | string |  |
| `co` | string |  |
| `country` | string |  |
| `county` | string |  |
| `defaultHours` | number |  |
| `distributionCodes` | string |  |
| `eeoClass` | string |  |
| `emailAddress` | string |  |
| `empStatus` | string |  |
| `empType` | string |  |
| `firstName` | string |  |
| `flsaOTExempt` | boolean |  |
| `guidfield` | string |  |
| `hireDate` | date |  |
| `homePhone` | string |  |
| `id` | string |  |
| `jobCode` | string |  |
| `lastChange` | date |  |
| `lastChangeUser` | string |  |
| `lastName` | string |  |
| `lastRaiseAmount` | number |  |
| `lastRaiseDate` | date |  |
| `lastRaiseReason` | string |  |
| `lastReviewDate` | date |  |
| `lastReviewRating` | string |  |
| `mailStop` | string |  |
| `middleName` | string |  |
| `nextRaiseDate` | date |  |
| `nextReviewDate` | date |  |
| `nickname` | string |  |
| `payFrequency` | string |  |
| `payGrade` | string |  |
| `payGroup` | string |  |
| `positionCode` | string |  |
| `positionInfoLocked` | boolean |  |
| `priorLastName` | string |  |
| `probation` | boolean |  |
| `ratePer` | string |  |
| `rehireDate` | date |  |
| `salutation` | string |  |
| `seasonal` | boolean |  |
| `soc` | string |  |
| `state` | string |  |
| `supervisorID` | string |  |
| `supervisorName` | string |  |
| `surname` | string |  |
| `termDate` | date |  |
| `termReason` | string |  |
| `tipped` | string |  |
| `title` | string |  |
| `user7` | string |  |
| `wageType` | string |  |
| `wcc` | string |  |
| `workPhone` | string |  |
| `workPhoneExt` | string |  |
| `workState` | string |  |
| `zip` | string |  |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /load` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-employee.md) for the provider-specific parameters and requirements.

