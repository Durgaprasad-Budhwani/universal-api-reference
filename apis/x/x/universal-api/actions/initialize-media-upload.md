# X: Initialize Media Upload



```
POST https://connect.mindcloud.co/v1/universal/x/latest/actions/initialize-media-upload
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a X `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/x/latest/actions/initialize-media-upload" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/x/latest/actions/initialize-media-upload', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `totalBytes` | number | no | Exact total file size in bytes; maximum 17179869184, subject to account limits. |
| `mediaType` | list<string> | no | MIME type of the uploaded file. One of: `image/bmp`, `image/gif`, `image/jpeg`, `image/pjpeg`, `image/png`, `image/tiff`, `image/webp`, `model/gltf-binary`, `model/vnd.usdz+zip`, `text/srt`, `text/vtt`, `video/mp2t`, `video/mp4`, `video/quicktime`, `video/webm`. |
| `mediaCategory` | list<string> | no | Use tweet_video for a regular video post. One of: `amplify_video`, `dm_gif`, `dm_image`, `dm_video`, `subtitles`, `tweet_gif`, `tweet_image`, `tweet_video`. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `additionalOwners[]` | array<string> | no | User IDs granted access to the uploaded media. |
| `shared` | boolean | no | Whether this media is shared. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native X API returns.

## Native endpoint

Through the native X API, this operation is `POST /2/media/upload/initialize` (base URL `https://api.x.com`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/initialize-media-upload.md) for the provider-specific parameters and requirements.

