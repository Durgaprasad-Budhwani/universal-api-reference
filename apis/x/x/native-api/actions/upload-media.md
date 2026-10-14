# Upload Media with X

## Endpoint

- **Method:** `POST`
- **Path:** `/2/media/upload`
- **Base URL:** `https://api.x.com`
- **Official documentation:** [Upload Media](https://docs.x.com/x-api/media/upload-media)

## Headers

Send these additional headers for this operation:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/json` |

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `media` | body | `string` | yes | Base64-encoded file contents for the JSON upload request. |
| `media_category` | body | `list<string>` | yes | Accepted values: `dm_gif`, `dm_image`, `dm_video`, `subtitles`, `tweet_gif`, `tweet_image`, `tweet_video`. |
| `additional_owners` | body | `string` | no | User IDs that can use this media, sent as a comma-separated list. Send multiple values as a string separated by `,`. |
