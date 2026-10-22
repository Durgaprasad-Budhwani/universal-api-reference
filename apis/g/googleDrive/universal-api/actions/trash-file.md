# Google Drive: Trash File



```
PUT https://connect.mindcloud.co/v1/universal/googleDrive/latest/actions/trash-file
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Google Drive `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X PUT "https://connect.mindcloud.co/v1/universal/googleDrive/latest/actions/trash-file" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "fileId": "string"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/googleDrive/latest/actions/trash-file', {
  method: 'PUT',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "fileId": "string"
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `fileId` | list<string> | yes | One file ID string to move to Trash. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "id": "string",
      "mimeType": "string",
      "name": "Ava Chen",
      "parents": [
        "string"
      ],
      "trashed": true
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `id` | string | File ID. |
| `mimeType` | string | File MIME type. |
| `name` | string | File name. |
| `parents` | array<string> | Parent folder IDs. |
| `trashed` | boolean | True after the file is moved to Trash. |

## Native endpoint

Through the native Google Drive API, this operation is `PATCH /drive/v3/files/:fileId` (base URL `https://www.googleapis.com`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/trash-file.md) for the provider-specific parameters and requirements.

