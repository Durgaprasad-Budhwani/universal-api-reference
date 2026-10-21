# Download File with Box

## Endpoint

- **Method:** `GET`
- **Path:** `/files/:file_id/content`
- **Base URL:** `https://api.box.com/2.0`
- **Official documentation:** [Download File](https://developer.box.com/reference/get-files-id-content)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `file_id` | path | `string` | yes | The Box file ID to download. |
| `version` | query | `string` | no | Optional file version ID to download. |
