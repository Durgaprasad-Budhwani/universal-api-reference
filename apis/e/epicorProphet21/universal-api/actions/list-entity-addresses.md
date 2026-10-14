# Epicor Prophet 21: List Entity Addresses



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-entity-addresses
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-entity-addresses?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-entity-addresses?${params}`, {
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
      "alternative1099Name": "Ava Chen",
      "centralFaxNumber": "string",
      "centralPhoneNumber": "string",
      "corpAddressId": 1,
      "emailAddress": "ava@example.com",
      "incorporated": "string",
      "mailAddress1": "string",
      "mailAddress2": "string",
      "mailAddress3": "string",
      "mailCity": "string",
      "mailCountry": "string",
      "mailPostalCode": "string",
      "mailState": "string",
      "name": "Ava Chen",
      "nameControl": "Ava Chen",
      "objectName": "Ava Chen",
      "physAddress1": "string",
      "physAddress2": "string",
      "physAddress3": "string",
      "physCity": "string",
      "physCountry": "string",
      "physCounty": "string",
      "physPostalCode": "string",
      "physState": "string",
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
| `alternative1099Name` | string |  |
| `centralFaxNumber` | string |  |
| `centralPhoneNumber` | string |  |
| `corpAddressId` | number |  |
| `emailAddress` | string |  |
| `incorporated` | string |  |
| `mailAddress1` | string |  |
| `mailAddress2` | string |  |
| `mailAddress3` | string |  |
| `mailCity` | string |  |
| `mailCountry` | string |  |
| `mailPostalCode` | string |  |
| `mailState` | string |  |
| `name` | string |  |
| `nameControl` | string |  |
| `objectName` | string |  |
| `physAddress1` | string |  |
| `physAddress2` | string |  |
| `physAddress3` | string |  |
| `physCity` | string |  |
| `physCountry` | string |  |
| `physCounty` | string |  |
| `physPostalCode` | string |  |
| `physState` | string |  |
| `url` | string |  |
| `userDefinedFields` | object |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /api/entity/addresses` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-entity-addresses.md) for the provider-specific parameters and requirements.

