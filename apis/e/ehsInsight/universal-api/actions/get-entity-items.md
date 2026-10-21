# EHS Insight: Get Entity Items



```
GET https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-entity-items
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a EHS Insight `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-entity-items?connectionId=$CONNECTION_ID&entityName=Asset" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "entityName": "Asset"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-entity-items?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as query string parameters ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `entityName` | string | yes | Default: `Asset`. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `customparams` | string | no | Optional provider-specific query string segment appended after the list route. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "rowUID": "string",
      "createdDtm": "string",
      "updatedDtm": "string",
      "changeToken": "string",
      "title": "string",
      "acquiredDate": "string",
      "businessEntity": "string",
      "isEnabled": 1,
      "assetPhoto": "string",
      "number": "string",
      "type": "string",
      "make": "string",
      "model": "string",
      "year": 1,
      "color": "string",
      "serial": "string",
      "state": "string",
      "plate": "string",
      "marketValue": 1,
      "comments": "string",
      "entityName": "Ava Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `rowUID` | string |  |
| `createdDtm` | string |  |
| `updatedDtm` | string |  |
| `changeToken` | string |  |
| `title` | string |  |
| `acquiredDate` | string |  |
| `businessEntity` | string |  |
| `isEnabled` | number |  |
| `assetPhoto` | string |  |
| `number` | string |  |
| `type` | string |  |
| `make` | string |  |
| `model` | string |  |
| `year` | number |  |
| `color` | string |  |
| `serial` | string |  |
| `state` | string |  |
| `plate` | string |  |
| `marketValue` | number |  |
| `comments` | string |  |
| `entityName` | string |  |

## Native endpoint

Through the native EHS Insight API, this operation is `GET /v4/entity/:entityName/list?:customparams` (base URL `https://{{credentials.companyName}}.ehsinsight.com/api`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-entity-items.md) for the provider-specific parameters and requirements.

