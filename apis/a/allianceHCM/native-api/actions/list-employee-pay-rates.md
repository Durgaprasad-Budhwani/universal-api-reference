# List Employee Pay Rates with Alliance HCM

## Endpoint

- **Method:** `POST`
- **Path:** `/load`
- **Base URL:** `https://api2.hralliance.net/AllPayRestData.svc/json`
- **Official documentation:** [List Employee Pay Rates](https://api2.hralliance.net/JSONAPIManual.html#Load)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `companyCode` | body | `list<string>` | yes | — |
| `employeeId` | body | `string` | no | Optional. Use id from an employee or change record. Leave empty to list rates for all employees in the chosen company. Maximum length: 10. |
| `rateCode` | body | `string` | no | Optional. Enter a known rate code such as Base, or leave empty to include every pay rate. Maximum length: 10. |
