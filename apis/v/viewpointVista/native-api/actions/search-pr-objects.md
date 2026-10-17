# Search PR Objects with Viewpoint Vista

Search objects found in Viewpoint® Vista™ Payroll (PR) programs.

## Endpoint

- **Method:** `POST`
- **Path:** `v1/direct/subscribers/:subscriber_code/vista/:api/2/data/:object/cache/search`
- **Base URL:** `https://api.xchange.trimble.com/connect/`
- **API:** REST
- **Official documentation:** [Search PR Objects](https://direct-api.xchange.trimble.com/reference/get-directsubscriberssubscriber_codevistasm2datacustomerscache)

## Capabilities

This operation supports [filtering](../README.md#filtering).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `modifiedUtcAfter` | body | `date` | no | — |
| `object` | path | `list<string>` | yes | Specify the type of Object from the User Defined Tables V2 Direct API that you'd like to retrieve. Accepted values: `automatic_earnings`, `class_templates`, `classes`, `company_parameters`, `craft_templates`, `crafts`, `crews`, `dedn_liab_codes`, `departments`, `earning_codes`, `employee_daily_times`, `employee_dedn_liabs`, `employee_leave_history`, `employee_leaves`, `employees`, `employees_lite`, `groups`, `insurance_codes`, `leave_batch_entries`, `leave_batches`, `leave_codes`, `locals`, `pay_periods`, `pay_sequences`, `race_codes`, `states`, `templates`, `time_batch_entries`, `time_batches`, `time_entries`. |
| `modifiedUtcBefore` | body | `date` | no | — |
