# Upload Instagram Container Video with Facebook

## Endpoint

- **Method:** `POST`
- **Path:** `https://rupload.facebook.com/ig-api-upload/v26.0/:containerId`
- **Base URL:** `https://graph.facebook.com/v25.0`
- **Official documentation:** [Upload Instagram Container Video](https://developers.facebook.com/documentation/instagram-platform/instagram-graph-api/reference/ig-user/media)

## Headers

Send these additional headers for this operation:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/octet-stream` |

## Parameters

| Parameter | Location | Type | Required |
| --- | --- | --- | --- |
| `containerId` | path | `string` | yes |
| `video` | body | `file` | yes |
