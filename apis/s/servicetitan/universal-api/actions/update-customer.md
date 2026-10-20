# ServiceTitan: Update Customer

Updates an existing customer in ServiceTitan.

```
PUT https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-customer
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-customer" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "id": "string"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/update-customer', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "id": "string"
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `address.street` | string | no |  |
| `customFields[].typeId` | number | no |  |
| `externalData.applicationGuid` | string | no |  |
| `externalData.externalData[].key` | string | no |  |
| `name` | string | no |  |
| `address.unit` | string | no |  |
| `customFields[].value` | boolean | no |  |
| `externalData.externalData[]` | array | no |  |
| `externalData.externalData[].value` | string | no |  |
| `type` | string | no | Residential or commercial |
| `address` | object<object> | no | Bill-To address of the customer record |
| `address.city` | string | no |  |
| `address.state` | string | no |  |
| `customFields[]` | array<object> | no |  |
| `address.zip` | string | no |  |
| `externalData` | object | no |  |
| `address.country` | string | no |  |
| `doNotMail` | boolean | no | Default: `false`. |
| `id` | string | yes |  |
| `address.longitude` | number | no |  |
| `doNotService` | boolean | no | Default: `false`. |
| `active` | boolean | no | Customer has been flagged as “active” ar "innactive" |
| `address.latitude` | number | no |  |
| `tagTypeIds[]` | array<number> | no |  |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native ServiceTitan API returns.

## Native endpoint

Through the native ServiceTitan API, this operation is `PATCH crm/v2/tenant/{{credentials.tenant}}/customers/:id` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/update-customer.md) for the provider-specific parameters and requirements.

