# LinkedIn: Finalize Video Upload

Finalizes a video upload in LinkedIn.

```
PUT https://connect.mindcloud.co/v1/universal/linkedin/latest/actions/finalize-video-upload
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a LinkedIn `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/linkedin/latest/actions/finalize-video-upload" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "finalizeUploadRequest": {},
  "finalizeUploadRequest.video": "urn:li:video:C4D10AQGdk0RzRUup4A",
  "finalizeUploadRequest.uploadToken": "AQEDASBASD...",
  "finalizeUploadRequest.uploadedPartIds[]": "part-id-1,part-id-2"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/linkedin/latest/actions/finalize-video-upload', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "finalizeUploadRequest": {},
    "finalizeUploadRequest.video": "urn:li:video:C4D10AQGdk0RzRUup4A",
    "finalizeUploadRequest.uploadToken": "AQEDASBASD...",
    "finalizeUploadRequest.uploadedPartIds[]": "part-id-1,part-id-2"
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `finalizeUploadRequest` | object | yes |  |
| `finalizeUploadRequest.video` | string | yes | Example: `urn:li:video:C4D10AQGdk0RzRUup4A`. |
| `finalizeUploadRequest.uploadToken` | string | yes | Example: `AQEDASBASD...`. |
| `finalizeUploadRequest.uploadedPartIds[]` | array<string> | yes | Array of uploaded part IDs returned by LinkedIn upload instructions. Example: `part-id-1,part-id-2`. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native LinkedIn API returns.

## Native endpoint

Through the native LinkedIn API, this operation is `POST /rest/videos?action=finalizeUpload` (base URL `https://api.linkedin.com`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/finalize-video-upload.md) for the provider-specific parameters and requirements.

