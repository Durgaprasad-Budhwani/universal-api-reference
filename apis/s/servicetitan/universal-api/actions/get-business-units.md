# ServiceTitan: Get Business Units



```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-business-units
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-business-units?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-business-units?${params}`, {
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
| `active` | boolean | no |  |
| `includeTotal` | boolean | no |  |
| `modifiedOnOrAfter` | string | no |  |
| `name` | string | no |  |
| `createdBefore` | string | no |  |
| `createdOnOrAfter` | string | no |  |
| `externalDataApplicationGuid` | string | no |  |
| `ids` | string | no |  |
| `modifiedBefore` | string | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Ava Chen",
      "officialName": "Ava Chen",
      "active": true,
      "email": "ava@example.com",
      "phoneNumber": "string",
      "currency": "string",
      "address": "string",
      "invoiceHeader": "string",
      "invoiceMessage": "string",
      "defaultTaxRate": 1,
      "authorizationParagraph": "string",
      "acknowledgementParagraph": "string",
      "conceptCode": "string",
      "division": {
        "id": 1,
        "name": "Ava Chen"
      },
      "tenant": {
        "conceptCode": "string",
        "id": 1,
        "modifiedOn": "string",
        "name": "Ava Chen"
      },
      "tagTypeIds": [
        "string"
      ],
      "materialSku": {},
      "quickbooksClass": {},
      "accountCode": {},
      "franchiseId": {},
      "corporateContractNumber": {},
      "trade": {},
      "externalData": {},
      "certifiedSentriconSpecialistCode": {},
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
| `id` | number |  |
| `name` | string |  |
| `officialName` | string |  |
| `active` | boolean |  |
| `email` | string |  |
| `phoneNumber` | string |  |
| `currency` | string |  |
| `address` | string |  |
| `invoiceHeader` | string |  |
| `invoiceMessage` | string |  |
| `defaultTaxRate` | number |  |
| `authorizationParagraph` | string |  |
| `acknowledgementParagraph` | string |  |
| `conceptCode` | string |  |
| `division` | object |  |
| `tenant` | object |  |
| `tagTypeIds` | array |  |
| `materialSku` | object |  |
| `quickbooksClass` | object |  |
| `accountCode` | object |  |
| `franchiseId` | object |  |
| `corporateContractNumber` | object |  |
| `trade` | object |  |
| `externalData` | object |  |
| `certifiedSentriconSpecialistCode` | object |  |
| `createdOn` | string |  |
| `modifiedOn` | string |  |
| `division.id` | number |  |
| `division.name` | string |  |
| `tenant.conceptCode` | string |  |
| `tenant.id` | number |  |
| `tenant.modifiedOn` | string |  |
| `tenant.name` | string |  |

## Native endpoint

Through the native ServiceTitan API, this operation is `GET settings/v2/tenant/{{credentials.tenant}}/business-units` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/get-business-units.md) for the provider-specific parameters and requirements.

