# Microsoft Exchange: Get User Message Attachment

Retrieves an attachment from a message in a user's mailbox.

```
GET https://connect.mindcloud.co/v1/universal/microsoftExchange/latest/actions/get-user-message-attachment
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Microsoft Exchange `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/microsoftExchange/latest/actions/get-user-message-attachment?connectionId=$CONNECTION_ID&userIdOrPrincipalName=user%40company.com%20or%20Entra%20user%20id&messageId=AAMkAG...&attachmentId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "userIdOrPrincipalName": "user@company.com or Entra user id",
  "messageId": "AAMkAG...",
  "attachmentId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/microsoftExchange/latest/actions/get-user-message-attachment?${params}`, {
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
| `userIdOrPrincipalName` | string | yes | The Microsoft Graph user id or userPrincipalName of the mailbox that holds the message. Example: `user@company.com or Entra user id`. |
| `messageId` | string | yes | The Exchange message ID that contains the attachments. Example: `AAMkAG...`. |
| `attachmentId` | string | yes | The attachment ID returned by List User Message Attachments. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "contentBytes": "string",
      "contentType": "string",
      "id": "string",
      "isInline": true,
      "lastModifiedDateTime": "2026-05-07T12:00:00.000Z",
      "name": "Ava Chen",
      "size": 1
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `contentBytes` | string | The base64-encoded file content. |
| `contentType` | string | The attachment MIME type. |
| `id` | string | The attachment ID. |
| `isInline` | boolean | Whether the attachment is inline. |
| `lastModifiedDateTime` | date | When the attachment was last modified. |
| `name` | string | The attachment file name. |
| `size` | number | The attachment size in bytes. |

## Native endpoint

Through the native Microsoft Exchange API, this operation is `GET /v1.0/users/:userIdOrPrincipalName/messages/:messageId/attachments/:attachmentId` (base URL `https://graph.microsoft.com`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-user-message-attachment.md) for the provider-specific parameters and requirements.

