# Viewpoint Vista: List SM Objects

Represents data found in Viewpoint® Vista™ SM programs.

```
GET https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-sm-objects
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Viewpoint Vista `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-sm-objects?connectionId=$CONNECTION_ID&object=ag_services" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "object": "ag_services"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-sm-objects?${params}`, {
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
| `modifiedUTCSince` | string | no | Specify a datetime against which to filter the results. When specified the result will be ordered oldest __modifiedUTC to newest. Example `2019-12-11T20:16:58.3419275Z`. ( Optional ) If unspecified, all cached objects will be returned. |
| `object` | list<string> | yes | Specify the type of Object from the Service Management V2 Direct API that you'd like to retrieve. One of: `ag_services`, `agreements`, `call_handlers`, `cost_types`, `customers`, `departments`, `invoice_headers`, `service_centers`, `service_sites`, `serviceable_items`, `standard_items`, `wo_trips`, `wo_work_completeds`, `work_order_quotes`, `work_orders`. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native Viewpoint Vista API returns.

## Native endpoint

Through the native Viewpoint Vista API, this operation is `GET v1/direct/subscribers/:subscriber_code/vista/:api/2/data/:object/cache` (base URL `https://api.xchange.trimble.com/connect/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-sm-objects.md) for the provider-specific parameters and requirements.

