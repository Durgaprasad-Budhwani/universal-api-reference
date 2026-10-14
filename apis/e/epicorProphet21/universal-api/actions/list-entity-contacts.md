# Epicor Prophet 21: List Entity Contacts



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-entity-contacts
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-entity-contacts?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-entity-contacts?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```



## Response

```json
{
  "success": true,
  "data": [
    {
      "addressId": 1,
      "beeper": "string",
      "cellular": "string",
      "cellularExt": "string",
      "class1id": "string",
      "class2id": "string",
      "class3id": "string",
      "class4id": "string",
      "class5id": "string",
      "comments": "string",
      "deleteFlag": "string",
      "directFax": "string",
      "directPhone": "string",
      "emailAddress": "ava@example.com",
      "faxExt": "string",
      "firstName": "Ava",
      "homeAddress1": "string",
      "homeAddress2": "string",
      "homeEmailAddress": "ava@example.com",
      "homeFax": "string",
      "homePhone": "string",
      "id": "string",
      "lastName": "Chen",
      "loginId": "string",
      "mailstop": "string",
      "mi": "string",
      "noOfCycleDays": 1,
      "objectName": "Ava Chen",
      "phoneExt": "string",
      "salutation": "string",
      "title": "string",
      "url": "https://example.com",
      "userDefinedFields": {}
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `addressId` | number |  |
| `beeper` | string |  |
| `cellular` | string |  |
| `cellularExt` | string |  |
| `class1id` | string |  |
| `class2id` | string |  |
| `class3id` | string |  |
| `class4id` | string |  |
| `class5id` | string |  |
| `comments` | string |  |
| `deleteFlag` | string |  |
| `directFax` | string |  |
| `directPhone` | string |  |
| `emailAddress` | string |  |
| `faxExt` | string |  |
| `firstName` | string |  |
| `homeAddress1` | string |  |
| `homeAddress2` | string |  |
| `homeEmailAddress` | string |  |
| `homeFax` | string |  |
| `homePhone` | string |  |
| `id` | string |  |
| `lastName` | string |  |
| `loginId` | string |  |
| `mailstop` | string |  |
| `mi` | string |  |
| `noOfCycleDays` | number |  |
| `objectName` | string |  |
| `phoneExt` | string |  |
| `salutation` | string |  |
| `title` | string |  |
| `url` | string |  |
| `userDefinedFields` | object |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /api/entity/contacts` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-entity-contacts.md) for the provider-specific parameters and requirements.

