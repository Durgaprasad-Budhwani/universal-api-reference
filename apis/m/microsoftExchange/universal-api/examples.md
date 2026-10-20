# Microsoft Exchange Universal API Examples

These examples use the MindCloud API key and Microsoft Exchange connection described in [authentication.md](authentication.md). Replace `$CONNECTION_ID` with the connection ID you copied from the Connections page.

## List User Folders

Finds messages in a user's mailbox.

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/microsoftExchange/latest/actions/list-user-folders?connectionId=$CONNECTION_ID&userIdOrPrincipalName=user%40company.com%20or%20Entra%20user%20id" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "userIdOrPrincipalName": "user@company.com or Entra user id"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/microsoftExchange/latest/actions/list-user-folders?${params}`, {
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
      "attachments": [
        {
          "contentType": "string",
          "id": "string",
          "isInline": true,
          "name": "Ava Chen"
        }
      ],
      "bccRecipients": [
        {
          "emailAddress": {
            "address": "ava@example.com",
            "name": "ava@example.com"
          }
        }
      ],
      "bodyPreview": "string",
      "ccRecipients": [
        {
          "emailAddress": {
            "address": "ava@example.com",
            "name": "ava@example.com"
          }
        }
      ],
      "from": {
        "emailAddress": {
          "address": "ava@example.com",
          "name": "ava@example.com"
        }
      },
      "hasAttachments": true,
      "id": "string",
      "importance": "string",
      "isRead": true,
      "receivedDateTime": "2026-05-07T12:00:00.000Z",
      "sender": {
        "emailAddress": {
          "address": "ava@example.com",
          "name": "ava@example.com"
        }
      },
      "sentDateTime": "2026-05-07T12:00:00.000Z",
      "subject": "string",
      "toRecipients": [
        {
          "emailAddress": {
            "address": "ava@example.com",
            "name": "ava@example.com"
          }
        }
      ],
      "webLink": "https://example.com"
    }
  ],
  "meta": {}
}
```

See the full [List User Folders action reference](actions/list-user-folders.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/microsoftExchange/latest/actions/list-user-folders).

## Add File Attachment to Message

Creates a file attachment on a message in Microsoft Exchange.

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/microsoftExchange/latest/actions/add-file-attachment-to-message" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "messageId": "string",
  "name": "Ava Chen",
  "contentType": "text/plain",
  "contentBytes": "string"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/microsoftExchange/latest/actions/add-file-attachment-to-message', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "messageId": "string",
    "name": "Ava Chen",
    "contentType": "text/plain",
    "contentBytes": "string"
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
      "@odata": {
        "type": "string"
      },
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

See the full [Add File Attachment to Message action reference](actions/add-file-attachment-to-message.md), or [try it interactively](https://mindcloud.co/docs/universal/rest/microsoftExchange/latest/actions/add-file-attachment-to-message).
