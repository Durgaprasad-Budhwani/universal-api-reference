# Zoho CRM: Create Registrations



```
POST https://connect.mindcloud.co/v1/universal/zohoCRM/latest/actions/create-registrations-batch
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Zoho CRM `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/zohoCRM/latest/actions/create-registrations-batch" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "data[]": [
    {}
  ]
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/zohoCRM/latest/actions/create-registrations-batch', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "data[]": [{}]
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `data[]` | array<object> | yes | Zoho CRM records to create. Each array item is sent as one record. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "data": [
        {
          "code": "string",
          "details": {
            "Created_By": {
              "id": "string",
              "name": "Ava Chen"
            },
            "Created_Time": "2026-05-07T12:00:00.000Z",
            "id": "string",
            "Modified_By": {
              "id": "string",
              "name": "Ava Chen"
            },
            "Modified_Time": "2026-05-07T12:00:00.000Z"
          },
          "message": "string",
          "status": "string"
        }
      ]
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `data[].code` | string | Zoho CRM result code for the record. |
| `data[].details.Created_By.id` | string | ID of the Zoho CRM user who created the record. |
| `data[].details.Created_By.name` | string | Name of the Zoho CRM user who created the record. |
| `data[].details.Created_Time` | date | Record creation time returned by Zoho CRM. |
| `data[].details.id` | string | Zoho CRM record ID created or updated. |
| `data[].details.Modified_By.id` | string | ID of the Zoho CRM user who modified the record. |
| `data[].details.Modified_By.name` | string | Name of the Zoho CRM user who modified the record. |
| `data[].details.Modified_Time` | date | Record modification time returned by Zoho CRM. |
| `data[].message` | string | Zoho CRM result message for the record. |
| `data[].status` | string | Zoho CRM result status for the record. |

## Native endpoint

Through the native Zoho CRM API, this operation is `POST /Registrations` (base URL `{{credentials.accessTokenRequest.api_domain}}/crm/v8`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/create-registrations-batch.md) for the provider-specific parameters and requirements.

