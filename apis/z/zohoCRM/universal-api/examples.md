# Zoho CRM Universal API Examples

These examples use the MindCloud API key and Zoho CRM connection described in [authentication.md](authentication.md). Replace `$CONNECTION_ID` with the connection ID you copied from the Connections page.

## Get Organization Details

Retrieves organization details from Zoho CRM.

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/zohoCRM/latest/actions/get-organization-details?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/zohoCRM/latest/actions/get-organization-details?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```

Example response:

```json
{
  "success": true,
  "data": [
    {
      "companyName": "Ava Chen",
      "countryCode": "string",
      "createdTime": "2026-05-07T12:00:00.000Z",
      "currency": "string",
      "id": "string",
      "phone": "string",
      "primaryEmail": "ava@example.com",
      "timeZone": "string",
      "zgid": "string"
    }
  ],
  "meta": {}
}
```

See the full [Get Organization Details action reference](actions/get-organization-details.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/zohoCRM/latest/actions/get-organization-details).

## Convert Lead

Converts a lead into CRM records in Zoho CRM.

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/zohoCRM/latest/actions/convert-lead" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "recordId": "7323083000000731821"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/zohoCRM/latest/actions/convert-lead', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "recordId": "7323083000000731821"
  })
});

const { success, data } = await response.json();
```

Example response:

```json
{
  "success": true,
  "data": [
    {
      "code": "string",
      "details": {
        "accounts": {
          "id": "string",
          "name": "Ava Chen"
        },
        "contacts": {
          "id": "string",
          "name": "Ava Chen"
        },
        "deals": {
          "id": "string",
          "name": "Ava Chen"
        }
      },
      "message": "string",
      "status": "string"
    }
  ],
  "meta": {}
}
```

See the full [Convert Lead action reference](actions/convert-lead.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/zohoCRM/latest/actions/convert-lead).
