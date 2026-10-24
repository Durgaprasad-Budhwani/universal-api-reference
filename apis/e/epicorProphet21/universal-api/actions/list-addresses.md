# Epicor Prophet 21: List Addresses



```
GET https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-addresses
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Epicor Prophet 21 `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-addresses?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-addresses?${params}`, {
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
| `select` | string | no | Comma-separated field names. Leave empty to return all available fields. Default: `id,name,mail_address1,mail_city,mail_state,mail_postal_code,mail_country,phys_address1,phys_city,phys_state,phys_postal_code,phys_country,central_phone_number,central_fax_number`. |
| `filter` | string | no | A Prophet 21 filter expression, such as customer_id eq 123. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "centralFaxNumber": "string",
      "centralPhoneNumber": "string",
      "id": "string",
      "mailAddress1": "string",
      "mailCity": "string",
      "mailCountry": "string",
      "mailPostalCode": "string",
      "mailState": "string",
      "name": "Ava Chen",
      "physAddress1": "string",
      "physCity": "string",
      "physCountry": "string",
      "physPostalCode": "string",
      "physState": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `centralFaxNumber` | string |  |
| `centralPhoneNumber` | string |  |
| `id` | string |  |
| `mailAddress1` | string |  |
| `mailCity` | string |  |
| `mailCountry` | string |  |
| `mailPostalCode` | string |  |
| `mailState` | string |  |
| `name` | string |  |
| `physAddress1` | string |  |
| `physCity` | string |  |
| `physCountry` | string |  |
| `physPostalCode` | string |  |
| `physState` | string |  |

## Native endpoint

Through the native Epicor Prophet 21 API, this operation is `GET /data/erp/views/v1/p21_view_address` (base URL `{{credentials.apiUrl}}`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-addresses.md) for the provider-specific parameters and requirements.

