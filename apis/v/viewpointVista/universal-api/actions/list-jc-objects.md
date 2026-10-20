# Viewpoint Vista: List JC Objects

Represents data found in Viewpoint® Vista™ JC programs.

```
GET https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-jc-objects
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Viewpoint Vista `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-jc-objects?connectionId=$CONNECTION_ID&object=budget_codes" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "object": "budget_codes"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-jc-objects?${params}`, {
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
| `object` | list<string> | yes | Specify the type of Object from the Job Cost V2 Direct API that you'd like to retrieve. One of: `budget_codes`, `change_orders`, `company_parameters`, `contract_cls_batches`, `contract_cls_entries`, `contract_headers`, `contract_items`, `contracts`, `cost_adj_bat_entries`, `cost_adj_batches`, `cost_detail`, `cost_detail_period`, `cost_types`, `departments`, `field_tickets`, `fixed_rate_templates`, `insurance_templates`, `job_costs`, `job_phases`, `jobs`, `liability_templates`, `mat_use_bat_entries`, `mat_use_batches`, `metric_conversions`, `original_estimates`, `phases`, `progress_bat_entries`, `progress_batches`, `proj_bat_entries`, `proj_batches`, `project_managers`, `projection_notes`, `std_item_codes`. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native Viewpoint Vista API returns.

## Native endpoint

Through the native Viewpoint Vista API, this operation is `GET v1/direct/subscribers/:subscriber_code/vista/:api/2/data/:object/cache` (base URL `https://api.xchange.trimble.com/connect/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-jc-objects.md) for the provider-specific parameters and requirements.

