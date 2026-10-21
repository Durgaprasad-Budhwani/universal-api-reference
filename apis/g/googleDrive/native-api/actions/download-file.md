# Download File with Google Drive

## Endpoint

- **Method:** `GET`
- **Path:** `/drive/v3/files/:fileId`
- **Base URL:** `https://www.googleapis.com`
- **Official documentation:** [Download File](https://developers.google.com/workspace/drive/api/reference/rest/v3/files/get)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | `string` | yes | ID of the binary file stored in Drive. Use Export File for native Google Docs, Sheets, or Slides. |
