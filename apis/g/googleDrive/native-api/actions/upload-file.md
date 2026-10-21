# Upload File with Google Drive

Uploads a new file to Google Drive.

## Endpoint

- **Method:** `POST`
- **Path:** `/upload/drive/v3/files`
- **Base URL:** `https://www.googleapis.com`
- **Official documentation:** [Upload File](https://developers.google.com/workspace/drive/api/reference/rest/v3/files/create)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileType` | path | `list` | yes | MIME type of the uploaded file. Choose PDF for .pdf or Excel (.xlsx) for .xlsx files. Accepted values: `application/pdf`, `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`, `application/vnd.openxmlformats-officedocument.wordprocessingml.document`, `image/gif`, `image/jpeg`, `image/png`. |
| `file` | body | `file` | yes | Base64-encoded file content or a direct download URL that works without interactive sign-in. PDF and Excel (.xlsx) are supported. Prefer a URL for larger files. This simple upload supports files up to 5 MB and creates the file without custom name or folder metadata. |
