# List Messages in Folder with Microsoft 365 Outlook

Retrieves messages from a mail folder in Microsoft 365 Outlook.

## Endpoint

- **Method:** `GET`
- **Path:** `/v1.0/me/mailFolders/{{mailFolderId}}/messages`
- **Base URL:** `https://graph.microsoft.com`
- **Official documentation:** [List Messages in Folder](https://learn.microsoft.com/en-us/graph/api/mailfolder-list-messages?view=graph-rest-1.0)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `mailFolderId` | path | `string` | yes | The mail folder ID or a well-known folder name such as inbox or archive. |
