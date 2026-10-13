# Get User Message Attachment with Microsoft Exchange

Retrieves an attachment from a message in a user's mailbox.

## Endpoint

- **Method:** `GET`
- **Path:** `/v1.0/users/:userIdOrPrincipalName/messages/:messageId/attachments/:attachmentId`
- **Base URL:** `https://graph.microsoft.com`
- **Official documentation:** [Get User Message Attachment](https://learn.microsoft.com/en-us/graph/api/attachment-get?view=graph-rest-1.0)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `userIdOrPrincipalName` | path | `string` | yes | The Microsoft Graph user id or userPrincipalName of the mailbox that holds the message. |
| `messageId` | path | `string` | yes | The Exchange message ID that contains the attachments. |
| `attachmentId` | path | `string` | yes | The attachment ID returned by List User Message Attachments. |
