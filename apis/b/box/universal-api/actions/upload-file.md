# Box: Upload File



```
POST https://connect.mindcloud.co/v1/universal/box/latest/actions/upload-file
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Box `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/box/latest/actions/upload-file" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "fileName": "report.pdf",
  "parentFolderId": "0",
  "file": "SG9sYSBCb3ggZGVzZGUgTWluZENsb3VkIQ=="
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/box/latest/actions/upload-file', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "fileName": "report.pdf",
    "parentFolderId": "0",
    "file": "SG9sYSBCb3ggZGVzZGUgTWluZENsb3VkIQ=="
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `fileName` | string | yes | The name of the new file to upload into Box. Example: `report.pdf`. |
| `parentFolderId` | string | yes | Parent Box folder ID. Use `0` to upload the file into the root folder. Default: `0`. Example: `0`. |
| `file` | file | yes | Paste a plain base64 string, a full data URL, or a public HTTPS file URL. Data URLs are stripped to raw base64 automatically before upload. Example: `SG9sYSBCb3ggZGVzZGUgTWluZENsb3VkIQ==`. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `fields` | string | no | Optional comma-separated list of file fields to include in the response. Example: `id,type,name,size,parent`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "contentCreatedAt": "string",
      "contentModifiedAt": "string",
      "createdAt": "string",
      "createdBy": {
        "id": "string",
        "login": "string",
        "name": "Ava Chen",
        "type": "string"
      },
      "description": "string",
      "etag": "string",
      "fileVersion": {
        "id": "string",
        "sha1": "string",
        "type": "string"
      },
      "id": "string",
      "itemStatus": "string",
      "modifiedAt": "string",
      "modifiedBy": {
        "id": "string",
        "login": "string",
        "name": "Ava Chen",
        "type": "string"
      },
      "name": "Ava Chen",
      "ownedBy": {
        "id": "string",
        "login": "string",
        "name": "Ava Chen",
        "type": "string"
      },
      "parent": {
        "etag": "string",
        "id": "string",
        "name": "Ava Chen",
        "sequenceId": "string",
        "type": "string"
      },
      "pathCollection": {
        "entries": [
          {
            "etag": {},
            "id": "string",
            "name": "Ava Chen",
            "sequenceId": {},
            "type": "string"
          }
        ],
        "totalCount": 1
      },
      "purgedAt": {},
      "sequenceId": "string",
      "sha1": "string",
      "sharedLink": {},
      "size": 1,
      "trashedAt": {},
      "type": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `contentCreatedAt` | string |  |
| `contentModifiedAt` | string |  |
| `createdAt` | string |  |
| `createdBy.id` | string |  |
| `createdBy.login` | string |  |
| `createdBy.name` | string |  |
| `createdBy.type` | string |  |
| `description` | string |  |
| `etag` | string |  |
| `fileVersion.id` | string |  |
| `fileVersion.sha1` | string |  |
| `fileVersion.type` | string |  |
| `id` | string |  |
| `itemStatus` | string |  |
| `modifiedAt` | string |  |
| `modifiedBy.id` | string |  |
| `modifiedBy.login` | string |  |
| `modifiedBy.name` | string |  |
| `modifiedBy.type` | string |  |
| `name` | string |  |
| `ownedBy.id` | string |  |
| `ownedBy.login` | string |  |
| `ownedBy.name` | string |  |
| `ownedBy.type` | string |  |
| `parent.etag` | string |  |
| `parent.id` | string |  |
| `parent.name` | string |  |
| `parent.sequenceId` | string |  |
| `parent.type` | string |  |
| `pathCollection.entries[].etag` | object |  |
| `pathCollection.entries[].id` | string |  |
| `pathCollection.entries[].name` | string |  |
| `pathCollection.entries[].sequenceId` | object |  |
| `pathCollection.entries[].type` | string |  |
| `pathCollection.totalCount` | number |  |
| `purgedAt` | object |  |
| `sequenceId` | string |  |
| `sha1` | string |  |
| `sharedLink` | object |  |
| `size` | number |  |
| `trashedAt` | object |  |
| `type` | string |  |

## Native endpoint

Through the native Box API, this operation is `POST https://upload.box.com/api/2.0/files/content`. The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/upload-file.md) for the provider-specific parameters and requirements.

