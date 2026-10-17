# Viewpoint Vista: Search PR Objects

Search objects found in Viewpoint® Vista™ Payroll (PR) programs.

```
GET https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/search-pr-objects
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Viewpoint Vista `connectionId` ([setup](../authentication.md)).

This action also supports [filtering](../filtering.md) (`where`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/search-pr-objects?connectionId=$CONNECTION_ID&object=automatic_earnings" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "object": "automatic_earnings"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/search-pr-objects?${params}`, {
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
| `modifiedUtcAfter` | date | no |  |
| `object` | list<string> | yes | Specify the type of Object from the User Defined Tables V2 Direct API that you'd like to retrieve. One of: `automatic_earnings`, `class_templates`, `classes`, `company_parameters`, `craft_templates`, `crafts`, `crews`, `dedn_liab_codes`, `departments`, `earning_codes`, `employee_daily_times`, `employee_dedn_liabs`, `employee_leave_history`, `employee_leaves`, `employees`, `employees_lite`, `groups`, `insurance_codes`, `leave_batch_entries`, `leave_batches`, `leave_codes`, `locals`, `pay_periods`, `pay_sequences`, `race_codes`, `states`, `templates`, `time_batch_entries`, `time_batches`, `time_entries`. |
| `modifiedUtcBefore` | date | no |  |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native Viewpoint Vista API returns.

## Native endpoint

Through the native Viewpoint Vista API, this operation is `POST v1/direct/subscribers/:subscriber_code/vista/:api/2/data/:object/cache/search` (base URL `https://api.xchange.trimble.com/connect/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/search-pr-objects.md) for the provider-specific parameters and requirements.

