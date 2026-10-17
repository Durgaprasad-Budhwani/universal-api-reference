# Alliance HCM: Native API Reference

A consolidated summary of Alliance HCM's API configuration and 15 documented operations, with links to official documentation.

- **Official docs:** https://api2.hralliance.net/JSONAPIManual.html
- **API base URL:** `https://api2.hralliance.net/AllPayRestData.svc/json`

## Authentication

### AllPay username, password, and API token

### Credentials

- **AllPay Username:** `username` · required
- **AllPay Password:** `password` · required · Enter your AllPay account password.
- **API Token:** `token` · required · The API token emailed by AllPay after choosing Reset API Token in Settings → Profile.

[Official authentication documentation](https://api2.hralliance.net/JSONAPIManual.html)

## API conventions

Request bodies use JSON.

Shared headers:

| Header | Value |
| --- | --- |
| `Accept` | `application/json` |
| `Content-Type` | `application/json` |

Responses from this API use JSON.

## Pagination

Use `queryOptions.batchSize` in the request body to set the page size. Use `queryOptions.startRecord` in the request body as the record offset; numbering starts at 0.

## Filtering

Send filters in the request body. Supported operators: `eq`.

## Sorting

Set the sort field with `sortOrder` in the request body. Use `asc` for ascending order and `desc` for descending order. Multiple sort fields can be combined.

## Endpoints (15 documented)

| Operation | Method & path | Vendor docs |
| --- | --- | --- |
| [Get Database Time](actions/get-database-time.md) | `POST /getDatabaseTime` | [docs](https://api2.hralliance.net/JSONAPIManual.html) |
| [Get Employee](actions/get-employee.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [Get Employee Change Log Sync Time](actions/get-employee-change-checkpoint.md) | `POST /getlastchangetime` | [docs](https://api2.hralliance.net/JSONAPIManual.html#getLastChangeTime) |
| [Get Employee Employment Details](actions/get-employee-employment-details.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [Get Pay Rate Change Checkpoint](actions/get-pay-rate-change-checkpoint.md) | `POST /getlastchangetime` | [docs](https://api2.hralliance.net/JSONAPIManual.html#getLastChangeTime) |
| [List Companies](actions/list-companies.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Changes](actions/list-employee-changes.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Employment Type Changes](actions/list-employee-employment-type-changes.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Job Changes](actions/list-employee-job-changes.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Pay History](actions/list-employee-pay-history.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Pay Rate Changes](actions/list-employee-pay-rate-changes.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Pay Rates](actions/list-employee-pay-rates.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Paycheck Line Items](actions/list-employee-paycheck-line-items.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employee Status Changes](actions/list-employee-status-changes.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html#Load) |
| [List Employees](actions/list-employees.md) | `POST /load` | [docs](https://api2.hralliance.net/JSONAPIManual.html) |
