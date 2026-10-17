# List Employees with Alliance HCM

## Endpoint

- **Method:** `POST`
- **Path:** `/load`
- **Base URL:** `https://api2.hralliance.net/AllPayRestData.svc/json`
- **Official documentation:** [List Employees](https://api2.hralliance.net/JSONAPIManual.html)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required |
| --- | --- | --- | --- |
| `companyCode` | body | `list<string>` | yes |
