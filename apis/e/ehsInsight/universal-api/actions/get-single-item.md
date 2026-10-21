# EHS Insight: Get Single Item



```
GET https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-single-item
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a EHS Insight `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-single-item?connectionId=$CONNECTION_ID&rowuid=26686a13-5b64-4b0d-9376-91f36cb728ff&entityName=UserContact" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "rowuid": "26686a13-5b64-4b0d-9376-91f36cb728ff",
  "entityName": "UserContact"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-single-item?${params}`, {
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
| `rowuid` | string | yes | Default: `26686a13-5b64-4b0d-9376-91f36cb728ff`. |
| `entityName` | string | yes | Default: `UserContact`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "rowUID": "string",
      "changeToken": "string",
      "createdDtm": "string",
      "updatedDtm": "string",
      "userContactNumber": "string",
      "userContactType": "string",
      "inviteSent": 1,
      "fullName": "Ava Chen",
      "userContactPhoto": "string",
      "userContactPhotoAttachmentUID": "string",
      "userContactPhotoContentType": "string",
      "userContactPhotoFileSize": "string",
      "language": "string",
      "languageOther": "string",
      "uIMode": "string",
      "uIModeOther": "string",
      "isEnabled": 1,
      "firstName": "Ava",
      "lastName": "Chen",
      "gender": "string",
      "genderOther": "string",
      "birthDate": "string",
      "homeAddress": "string",
      "homeCity": "string",
      "homeState": "string",
      "homeZip": "string",
      "phoneNumber": "string",
      "businessEntity": "string",
      "position": "string",
      "positionOther": "string",
      "employer": "string",
      "employerOther": "string",
      "supervisor": "string",
      "employeeID": "string",
      "hireDate": "string",
      "positionStartDate": "string",
      "industryStartDate": "string",
      "authProvider": "string",
      "authProviderOther": "string",
      "username": "Ava Chen",
      "emailAddress": "ava@example.com",
      "mobilePhoneNumber": "string",
      "roleAssignmentType": "string",
      "userContactPhotoPreviousVersions": [
        {}
      ],
      "trainingGroup": [
        {}
      ],
      "securityGroups": [
        {}
      ],
      "userRoles": [
        {}
      ]
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `rowUID` | string |  |
| `changeToken` | string |  |
| `createdDtm` | string |  |
| `updatedDtm` | string |  |
| `userContactNumber` | string |  |
| `userContactType` | string |  |
| `inviteSent` | number |  |
| `fullName` | string |  |
| `userContactPhoto` | string |  |
| `userContactPhotoAttachmentUID` | string |  |
| `userContactPhotoContentType` | string |  |
| `userContactPhotoFileSize` | string |  |
| `language` | string |  |
| `languageOther` | string |  |
| `uIMode` | string |  |
| `uIModeOther` | string |  |
| `isEnabled` | number |  |
| `firstName` | string |  |
| `lastName` | string |  |
| `gender` | string |  |
| `genderOther` | string |  |
| `birthDate` | string |  |
| `homeAddress` | string |  |
| `homeCity` | string |  |
| `homeState` | string |  |
| `homeZip` | string |  |
| `phoneNumber` | string |  |
| `businessEntity` | string |  |
| `position` | string |  |
| `positionOther` | string |  |
| `employer` | string |  |
| `employerOther` | string |  |
| `supervisor` | string |  |
| `employeeID` | string |  |
| `hireDate` | string |  |
| `positionStartDate` | string |  |
| `industryStartDate` | string |  |
| `authProvider` | string |  |
| `authProviderOther` | string |  |
| `username` | string |  |
| `emailAddress` | string |  |
| `mobilePhoneNumber` | string |  |
| `roleAssignmentType` | string |  |
| `userContactPhotoPreviousVersions` | array<object> |  |
| `trainingGroup` | array<object> |  |
| `securityGroups` | array<object> |  |
| `userRoles` | array<object> |  |

## Native endpoint

Through the native EHS Insight API, this operation is `GET /v4/entity/:entityName/fetch/:rowuid` (base URL `https://{{credentials.companyName}}.ehsinsight.com/api`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-single-item.md) for the provider-specific parameters and requirements.

