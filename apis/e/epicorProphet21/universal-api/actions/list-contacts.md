# Epicor Prophet 21: List Contacts



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-contacts
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-contacts?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-contacts?${params}`, {
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

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `select` | string | no | Comma-separated field names. Leave empty to return all available fields. Default: `id,address_id,address_name,first_name,last_name,email_address,home_email_address,email_address2,direct_phone`. |
| `filter` | string | no | A Prophet 21 filter expression, such as customer_id eq 123. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "addressId": "string",
      "addressName": "Ava Chen",
      "directPhone": "string",
      "emailAddress": "ava@example.com",
      "emailAddress2": "ava@example.com",
      "firstName": "Ava",
      "id": "string",
      "lastName": "Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `addressId` | string |  |
| `addressName` | string |  |
| `directPhone` | string |  |
| `emailAddress` | string |  |
| `emailAddress2` | string |  |
| `firstName` | string |  |
| `id` | string |  |
| `lastName` | string |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /data/erp/views/v1/p21_view_contacts` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-contacts.md) for the provider-specific parameters and requirements.

