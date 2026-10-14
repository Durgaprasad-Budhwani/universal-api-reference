# Initialize Media Upload with X

## Endpoint

- **Method:** `POST`
- **Path:** `/2/media/upload/initialize`
- **Base URL:** `https://api.x.com`
- **Official documentation:** [Initialize Media Upload](https://docs.x.com/x-api/media/initialize-media-upload)

## Headers

Send these additional headers for this operation:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/json` |

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `total_bytes` | body | `number` | no | Exact total file size in bytes; maximum 17179869184, subject to account limits. |
| `media_type` | body | `list<string>` | no | MIME type of the uploaded file. Accepted values: `image/bmp`, `image/gif`, `image/jpeg`, `image/pjpeg`, `image/png`, `image/tiff`, `image/webp`, `model/gltf-binary`, `model/vnd.usdz+zip`, `text/srt`, `text/vtt`, `video/mp2t`, `video/mp4`, `video/quicktime`, `video/webm`. |
| `media_category` | body | `list<string>` | no | Use tweet_video for a regular video post. Accepted values: `amplify_video`, `dm_gif`, `dm_image`, `dm_video`, `subtitles`, `tweet_gif`, `tweet_image`, `tweet_video`. |
| `additional_owners[]` | body | `array<string>` | no | User IDs granted access to the uploaded media. |
| `shared` | body | `boolean` | no | Whether this media is shared. |
