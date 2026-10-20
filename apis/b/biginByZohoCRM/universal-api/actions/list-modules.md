# Bigin by Zoho CRM: List Modules

Retrieves module details from Bigin by Zoho CRM.

```
GET https://connect.mindcloud.co/v1/universal/biginByZohoCRM/latest/actions/list-modules
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Bigin by Zoho CRM `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/biginByZohoCRM/latest/actions/list-modules?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/biginByZohoCRM/latest/actions/list-modules?${params}`, {
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
      "moduleName": "Ava Chen",
      "apiName": "Ava Chen",
      "singularLabel": "string",
      "pluralLabel": "string",
      "actualSingularLabel": "string",
      "actualPluralLabel": "string",
      "id": "string",
      "accessType": "string",
      "visibility": 1,
      "sequenceNumber": 1,
      "modifiedTime": "string",
      "generatedType": "string",
      "modifiedBy": {},
      "parentModule": {},
      "profileCount": 1,
      "businessCardFieldLimit": 1,
      "profiles": [
        {}
      ],
      "arguments": [
        {}
      ],
      "hasMoreProfiles": true,
      "globalSearchSupported": true,
      "deletable": true,
      "creatable": true,
      "editable": true,
      "viewable": true,
      "visible": true,
      "convertable": true,
      "apiSupported": true,
      "filterSupported": true,
      "showAsTab": true,
      "webformSupported": true,
      "inventoryTemplateSupported": true,
      "isBlueprintSupported": true,
      "presenceSubMenu": true,
      "triggersSupported": true,
      "quickCreate": true,
      "feedsRequired": true,
      "scoringSupported": true,
      "publicFieldsConfigured": true,
      "emailParserSupported": true,
      "emailTemplateSupport": true
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `moduleName` | string |  |
| `apiName` | string |  |
| `singularLabel` | string |  |
| `pluralLabel` | string |  |
| `actualSingularLabel` | string |  |
| `actualPluralLabel` | string |  |
| `id` | string |  |
| `accessType` | string |  |
| `visibility` | number |  |
| `sequenceNumber` | number |  |
| `modifiedTime` | string |  |
| `generatedType` | string |  |
| `modifiedBy` | object |  |
| `parentModule` | object |  |
| `profileCount` | number |  |
| `businessCardFieldLimit` | number |  |
| `profiles` | array<object> |  |
| `arguments` | array<object> |  |
| `hasMoreProfiles` | boolean |  |
| `globalSearchSupported` | boolean |  |
| `deletable` | boolean |  |
| `creatable` | boolean |  |
| `editable` | boolean |  |
| `viewable` | boolean |  |
| `visible` | boolean |  |
| `convertable` | boolean |  |
| `apiSupported` | boolean |  |
| `filterSupported` | boolean |  |
| `showAsTab` | boolean |  |
| `webformSupported` | boolean |  |
| `inventoryTemplateSupported` | boolean |  |
| `isBlueprintSupported` | boolean |  |
| `presenceSubMenu` | boolean |  |
| `triggersSupported` | boolean |  |
| `quickCreate` | boolean |  |
| `feedsRequired` | boolean |  |
| `scoringSupported` | boolean |  |
| `publicFieldsConfigured` | boolean |  |
| `emailParserSupported` | boolean |  |
| `emailTemplateSupport` | boolean |  |

## Native endpoint

Through the native Bigin by Zoho CRM API, this operation is `GET /settings/modules` (base URL `{{credentials.accessTokenRequest.api_domain}}/bigin/v2`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-modules.md) for the provider-specific parameters and requirements.

