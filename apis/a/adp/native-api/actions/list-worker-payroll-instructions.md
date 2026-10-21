# List Worker Payroll Instructions with ADP

## Endpoint

- **Method:** `GET`
- **Path:** `payroll/v1/workers/:aoid/payroll-instructions`
- **Base URL:** `https://api.adp.com/`
- **Official documentation:** [List Worker Payroll Instructions](https://developers.adp.com/apis/api-explorer/hcm-offrg-wfn/hcm-offrg-wfn-payroll-worker-payroll-instructions-v1-worker-payroll-instructions?operation=GET%2Fpayroll%2Fv1%2Fworkers%2F%7Baoid%7D%2Fpayroll-instructions#swagger)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `aoid` | path | `string` | yes | The ADP associate object identifier for the worker whose payroll instructions should be returned. |
