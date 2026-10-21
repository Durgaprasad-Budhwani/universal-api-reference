# EHS Insight: Get Hierarchy List



```
GET https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-hierarchy-list
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a EHS Insight `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-hierarchy-list?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/ehsInsight/latest/actions/get-hierarchy-list?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```



## Response

```json
{
  "success": true,
  "data": [
    {
      "rowUID": "string",
      "changeToken": "string",
      "title": "string",
      "startDate": "string",
      "endDate": "string",
      "comments": "string",
      "parentHierarchyUID": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `rowUID` | string |  |
| `changeToken` | string |  |
| `title` | string |  |
| `startDate` | string |  |
| `endDate` | string |  |
| `comments` | string |  |
| `parentHierarchyUID` | string |  |

## Native endpoint

Through the native EHS Insight API, this operation is `GET /v4/hierarchy/list` (base URL `https://{{credentials.companyName}}.ehsinsight.com/api`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-hierarchy-list.md) for the provider-specific parameters and requirements.

