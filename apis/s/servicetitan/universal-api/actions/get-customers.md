# ServiceTitan: Get Customers



```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-customers
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-customers?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/get-customers?${params}`, {
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
| `unit` | string | no |  |
| `city` | string | no |  |
| `state` | string | no |  |
| `country` | string | no |  |
| `phone` | string | no |  |
| `name` | string | no |  |
| `modifiedOnOrAfter` | string | no |  |
| `modifiedBefore` | string | no |  |
| `street` | string | no |  |
| `zip` | string | no |  |
| `createdOnOrAfter` | string | no |  |
| `createdBefore` | string | no |  |
| `active` | boolean | no |  |
| `ids` | string | no |  |
| `excludeAccountingChangesFromModifiedDateRange` | boolean | no | Excludes accounting changes such as balance adjustments from the modified date range. |
| `externalDataApplicationGuid` | string | no |  |
| `externalDataKey` | string | no |  |
| `externalDataValues` | string | no |  |
| `sort` | string | no | Applies sorting by the specified field: "?sort=+FieldName" for ascending order, "?sort=-FieldName" for descending order. Available fields are: Id, ModifiedOn, CreatedOn. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Ava Chen",
      "type": "string",
      "active": true,
      "balance": 1,
      "taxExempt": true,
      "doNotMail": true,
      "doNotService": true,
      "nationalAccount": true,
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
      "createdOn": "string",
      "createdById": 1,
      "modifiedOn": "string",
      "mergedToId": 1,
      "paymentTermId": 1,
      "creditLimit": 1,
      "creditLimitBalance": 1,
      "externalData": {}
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | number | ServiceTitan customer ID. |
| `name` | string | Customer name. |
| `type` | string | Customer type (Residential or Commercial). |
| `active` | boolean | Whether the customer is active. |
| `balance` | number | Outstanding account balance. |
| `taxExempt` | boolean | Whether the customer is tax exempt. |
| `doNotMail` | boolean | Whether the customer is excluded from mailings. |
| `doNotService` | boolean | Whether the customer is excluded from service. |
| `nationalAccount` | boolean | Whether the customer is a national account. |
| `address` | object | Billing address of the customer. |
| `customFields[]` | array<object> | Customer custom fields. |
| `tagTypeIds[]` | array<number> | Tag type IDs. |
| `createdOn` | string | Timestamp when the customer was created. |
| `createdById` | number | ID of the user who created the customer. |
| `modifiedOn` | string | Timestamp when the customer was last modified. |
| `mergedToId` | number | ID of the customer this customer was merged into. |
| `paymentTermId` | number | Payment term ID. |
| `creditLimit` | number | Credit limit. |
| `creditLimitBalance` | number | Credit limit balance. |
| `externalData` | object | External data associated with the customer. |
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

Through the native ServiceTitan API, this operation is `GET crm/v2/tenant/{{credentials.tenant}}/customers` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/get-customers.md) for the provider-specific parameters and requirements.

