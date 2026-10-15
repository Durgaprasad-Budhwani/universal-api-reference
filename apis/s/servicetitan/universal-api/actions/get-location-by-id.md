# ServiceTitan: Get Location By Id

Retrieves a location from ServiceTitan by ID.

```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-location-by-id
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-location-by-id?connectionId=$CONNECTION_ID&id=1" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "id": "1"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-location-by-id?${params}`, {
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
| `id` | number | yes |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Ava Chen",
      "customerId": 1,
      "active": true,
      "taxExempt": true,
      "taxZoneId": 1,
      "zoneId": 1,
      "mergedToId": 1,
      "address": {
        "city": "string",
        "country": "string",
        "latitude": 1,
        "longitude": 1,
        "state": "string",
        "street": "string",
        "unit": "string",
        "zip": "string"
      },
      "customFields": [
        [
          {}
        ]
      ],
      "tagTypeIds": [
        [
          1
        ]
      ],
      "externalData": {},
      "createdOn": "string",
      "createdById": 1,
      "modifiedOn": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | number | ServiceTitan location ID. |
| `name` | string | Location name. |
| `customerId` | number | ID of the location's customer. |
| `active` | boolean | Whether the location is active. |
| `taxExempt` | boolean | Whether the location is tax exempt. |
| `taxZoneId` | number | Tax zone ID. |
| `zoneId` | number | Zone ID. |
| `mergedToId` | number | ID of the location this location was merged into. |
| `address` | object | Location address. |
| `customFields[]` | array<object> | Location custom fields. |
| `tagTypeIds[]` | array<number> | Tag type IDs. |
| `externalData` | object | External data associated with the location. |
| `createdOn` | string | Timestamp when the location was created. |
| `createdById` | number | ID of the user who created the location. |
| `modifiedOn` | string | Timestamp when the location was last modified. |
| `address.city` | string | City. |
| `address.country` | string | Country. |
| `address.latitude` | number | Latitude. |
| `address.longitude` | number | Longitude. |
| `address.state` | string | State. |
| `address.street` | string | Street address. |
| `address.unit` | string | Unit. |
| `address.zip` | string | Postal code. |
| `customFields[].name` | string | Custom field name. |
| `customFields[].typeId` | number | Custom field type ID. |
| `customFields[].value` | string | Custom field value. |

## Native endpoint

Through the native ServiceTitan API, this operation is `GET crm/v2/tenant/{{credentials.tenant}}/locations/:id` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-location-by-id.md) for the provider-specific parameters and requirements.

