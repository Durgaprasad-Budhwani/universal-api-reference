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
| `file` | body | `file` | yes | Base64-encoded file content or a direct download URL that works without interactive sign-in. PDF and Excel (.xlsx) are supported. This action uploads content only. To set name and folder, call Move File after upload using the returned file ID. The Universal API execution timeout still applies. |
| `fileName` | path | `string` | no | Not accepted by Upload File. After uploading content, use Move File with the returned fileId and the desired name. |
| `parentFolderId` | path | `list<string>` | no | Not accepted by Upload File. After uploading content, use Move File with the returned fileId and the destination folder ID as addParents. |
