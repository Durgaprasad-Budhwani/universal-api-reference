# Upload File with Box

## Endpoint

- **Method:** `POST`
- **URL:** `https://upload.box.com/api/2.0/files/content`
- **Official documentation:** [Upload File](https://developer.box.com/reference/post-files-content)

## Headers

Send these additional headers for this operation:

| Header | Value |
| --- | --- |
| `Content-Type` | `multipart/form-data` |

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fileName` | body | `string` | yes | The name of the new file to upload into Box. |
| `parentFolderId` | body | `string` | yes | Parent Box folder ID. Use `0` to upload the file into the root folder. |
| `file` | body | `file` | yes | Paste a plain base64 string, a full data URL, or a public HTTPS file URL. Data URLs are stripped to raw base64 automatically before upload. |
| `fields` | query | `string` | no | Optional comma-separated list of file fields to include in the response. |
