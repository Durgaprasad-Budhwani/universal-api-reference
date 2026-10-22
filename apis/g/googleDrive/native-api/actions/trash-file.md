# Trash File with Google Drive

## Endpoint

- **Method:** `PATCH`
- **Path:** `/drive/v3/files/:fileId`
- **Base URL:** `https://www.googleapis.com`
- **Official documentation:** [Trash File](https://developers.google.com/workspace/drive/api/reference/rest/v3/files/update)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | `list<string>` | yes | One file ID string to move to Trash. |
