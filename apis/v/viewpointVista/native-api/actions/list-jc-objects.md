# List JC Objects with Viewpoint Vista

Represents data found in Viewpoint® Vista™ JC programs.

## Endpoint

- **Method:** `GET`
- **Path:** `v1/direct/subscribers/:subscriber_code/vista/:api/2/data/:object/cache`
- **Base URL:** `https://api.xchange.trimble.com/connect/`
- **API:** REST
- **Official documentation:** [List JC Objects](https://direct-api.xchange.trimble.com/reference/get-directsubscriberssubscriber_codevistasm2datacustomerscache)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `modifiedUTCSince` | query | `string` | no | Specify a datetime against which to filter the results.  When specified the result will be ordered oldest __modifiedUTC to newest.  Example `2019-12-11T20:16:58.3419275Z`.  ( Optional ) If unspecified, all cached objects will be returned. |
| `object` | path | `list<string>` | yes | Specify the type of Object from the Job Cost V2 Direct API that you'd like to retrieve. Accepted values: `budget_codes`, `change_orders`, `company_parameters`, `contract_cls_batches`, `contract_cls_entries`, `contract_headers`, `contract_items`, `contracts`, `cost_adj_bat_entries`, `cost_adj_batches`, `cost_detail`, `cost_detail_period`, `cost_types`, `departments`, `field_tickets`, `fixed_rate_templates`, `insurance_templates`, `job_costs`, `job_phases`, `jobs`, `liability_templates`, `mat_use_bat_entries`, `mat_use_batches`, `metric_conversions`, `original_estimates`, `phases`, `progress_bat_entries`, `progress_batches`, `proj_bat_entries`, `proj_batches`, `project_managers`, `projection_notes`, `std_item_codes`. |
