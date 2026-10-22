# Export File with Google Drive

Exports a Google Workspace document from Google Drive.

## Endpoint

- **Method:** `GET`
- **Path:** `/drive/v3/files/:fileId/export`
- **Base URL:** `https://www.googleapis.com`
- **Official documentation:** [Export File](https://developers.google.com/workspace/drive/api/reference/rest/v3/files/export)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileId` | path | `list` | yes | Select one Google Workspace file or pass its single ID string, for example {"fileId":"your-file-id"}. This dropdown selects one value; arrays and batches are not supported. Run a separate export for each file. With drive.file access, the file must be created by or explicitly authorized to this app. |
| `mimeType` | query | `list` | yes | The export format to request from Google Drive files.export. Accepted values: `application/pdf`, `application/rtf`, `application/vnd.oasis.opendocument.text`, `application/vnd.openxmlformats-officedocument.presentationml.presentation`, `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`, `application/vnd.openxmlformats-officedocument.wordprocessingml.document`, `text/plain`. |
