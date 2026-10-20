# Aspire: Post Attachment



```
POST https://connect.mindcloud.co/v1/universal/aspire/latest/actions/post-attachment
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Aspire `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/aspire/latest/actions/post-attachment" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "attachmentTypeId": 1,
  "fileName": "Ava Chen",
  "fileData": "string",
  "objectCode": "string",
  "objectId": 1
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/aspire/latest/actions/post-attachment', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "attachmentTypeId": 1,
    "fileName": "Ava Chen",
    "fileData": "string",
    "objectCode": "string",
    "objectId": 1
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `attachmentTypeId` | list<number> | yes |  |
| `fileName` | string | yes |  |
| `fileData` | file | yes | File content as a base64-encoded string. When the user attached a file in the chat, pass the attachment reference provided by the chat. |
| `objectCode` | list<string> | yes | Type of record receiving the attachment. Common values: WorkTicket (set objectId to workTicketID, not the ticket number), Opportunity (set objectId to opportunityID), and Receipt (set objectId to receiptID). Use listObjectCodes for the full list of supported values; do not guess the record type. |
| `objectId` | number | yes |  |
| `attachToInvoice` | boolean | no | Only valid for Opportunity attachments. For any other objectCode, omit this field entirely; Aspire rejects it even when false. |
| `exposeToCrew` | boolean | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "response": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `response` | string |  |

## Native endpoint

Through the native Aspire API, this operation is `POST /Attachments` (base URL `https://{{credentials.environment}}.youraspire.com/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/post-attachment.md) for the provider-specific parameters and requirements.

