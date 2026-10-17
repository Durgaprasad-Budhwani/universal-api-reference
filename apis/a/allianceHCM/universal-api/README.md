# <img src="https://images.mindcloud.co/apps/icons/alliance-hcm_1792020310025.png" alt="Alliance HCM logo" width="28" height="28"> Alliance HCM: Universal API

Alliance HCM: Read employees, employee changes, and pay rates

- **Interactive docs:** https://mindcloud.co/docs/universal/rest/allianceHCM/latest
- **Category:** Human Resources / HRIS
- **Actions:** 15
- **OpenAPI specification:** [openapi.json](openapi.json)
- **Vendor website:** https://alliancehcm.com/
- **Vendor API docs:** https://api2.hralliance.net/JSONAPIManual.html

## Quickstart

Every action below is called through one REST interface, authenticated with a MindCloud API key and a `connectionId`.

Read more in [authentication.md](authentication.md).

For example, to [Get Database Time](actions/get-database-time.md):

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-database-time?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

## Actions (15)

### Company

| Action | Method | Description |
| --- | --- | --- |
| [List Companies](actions/list-companies.md) | GET |  |

### Connection

| Action | Method | Description |
| --- | --- | --- |
| [Get Database Time](actions/get-database-time.md) | GET |  |

### Employee

| Action | Method | Description |
| --- | --- | --- |
| [Get Employee](actions/get-employee.md) | GET |  |
| [Get Employee Employment Details](actions/get-employee-employment-details.md) | GET |  |
| [List Employee Employment Type Changes](actions/list-employee-employment-type-changes.md) | GET |  |
| [List Employee Status Changes](actions/list-employee-status-changes.md) | GET |  |
| [List Employees](actions/list-employees.md) | GET |  |

### Employee Change

| Action | Method | Description |
| --- | --- | --- |
| [Get Employee Change Log Sync Time](actions/get-employee-change-checkpoint.md) | GET |  |
| [List Employee Changes](actions/list-employee-changes.md) | GET |  |

### Employee Job

| Action | Method | Description |
| --- | --- | --- |
| [List Employee Job Changes](actions/list-employee-job-changes.md) | GET |  |

### Employee Pay Rate

| Action | Method | Description |
| --- | --- | --- |
| [Get Pay Rate Change Checkpoint](actions/get-pay-rate-change-checkpoint.md) | GET |  |
| [List Employee Pay Rate Changes](actions/list-employee-pay-rate-changes.md) | GET |  |
| [List Employee Pay Rates](actions/list-employee-pay-rates.md) | GET |  |

### Employee Paycheck

| Action | Method | Description |
| --- | --- | --- |
| [List Employee Pay History](actions/list-employee-pay-history.md) | GET |  |
| [List Employee Paycheck Line Items](actions/list-employee-paycheck-line-items.md) | GET |  |

