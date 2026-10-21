# ADP: List Worker Additional Remunerations



```
GET https://connect.mindcloud.co/v1/universal/adp/latest/actions/list-worker-additional-remunerations
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ADP `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/adp/latest/actions/list-worker-additional-remunerations?connectionId=$CONNECTION_ID&aoid=string&assignmentId=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "aoid": "string",
  "assignmentId": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/adp/latest/actions/list-worker-additional-remunerations?${params}`, {
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
| `aoid` | string | yes | The ADP associate object identifier for the worker whose payroll instructions should be returned. |
| `assignmentId` | string | yes | The ID of the worker's work assignment. Find it in the worker record returned by Get Worker or List Workers, in workAssignments[].itemID. Choose the work assignment whose compensation information you want to retrieve. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native ADP API returns.

## Native endpoint

Through the native ADP API, this operation is `GET hr/worker-profile/v1/workers/:aoid/work-assignments/:assignmentId/additional-remunerations` (base URL `https://api.adp.com/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-worker-additional-remunerations.md) for the provider-specific parameters and requirements.

