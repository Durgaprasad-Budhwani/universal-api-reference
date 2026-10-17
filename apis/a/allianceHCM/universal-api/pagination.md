# Alliance HCM Universal API Pagination

Paginated list actions accept `limit` and `offset` as query parameters. MindCloud translates them into whatever pagination model Alliance HCM expects, so the request shape stays the same even when the native API uses pages or cursors.

| Parameter | Description |
| --- | --- |
| `limit` | Maximum number of records to return |
| `offset` | Number of records to skip |

Start with `offset=0`, add `limit` to the offset after each page, and stop when a page returns fewer rows than requested.

## Example

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/list-companies?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

## Alliance HCM actions that support pagination

- [List Companies](actions/list-companies.md)
- [List Employee Changes](actions/list-employee-changes.md)
- [List Employee Employment Type Changes](actions/list-employee-employment-type-changes.md)
- [List Employee Job Changes](actions/list-employee-job-changes.md)
- [List Employee Pay History](actions/list-employee-pay-history.md)
- [List Employee Pay Rate Changes](actions/list-employee-pay-rate-changes.md)
- [List Employee Pay Rates](actions/list-employee-pay-rates.md)
- [List Employee Paycheck Line Items](actions/list-employee-paycheck-line-items.md)
- [List Employee Status Changes](actions/list-employee-status-changes.md)
- [List Employees](actions/list-employees.md)
