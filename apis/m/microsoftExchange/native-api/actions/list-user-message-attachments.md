# List User Message Attachments with Microsoft Exchange

Finds the attachments on a message in a user's mailbox.

## Endpoint

- **Method:** `GET`
- **Path:** `/v1.0/users/:userIdOrPrincipalName/messages/:messageId/attachments`
- **Base URL:** `https://graph.microsoft.com`
- **Official documentation:** [List User Message Attachments](https://learn.microsoft.com/en-us/graph/api/message-list-attachments?view=graph-rest-1.0)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `userIdOrPrincipalName` | path | `string` | yes | The Microsoft Graph user id or userPrincipalName of the mailbox that holds the message. |
| `messageId` | path | `string` | yes | The Exchange message ID that contains the attachments. |
| `$select` | query | `string` | no | Comma-separated attachment fields to return. The default leaves out file content. |
