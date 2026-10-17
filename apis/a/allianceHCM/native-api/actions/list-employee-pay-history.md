# List Employee Pay History with Alliance HCM

## Endpoint

- **Method:** `POST`
- **Path:** `/load`
- **Base URL:** `https://api2.hralliance.net/AllPayRestData.svc/json`
- **Official documentation:** [List Employee Pay History](https://api2.hralliance.net/JSONAPIManual.html#Load)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `companyCode` | body | `list<string>` | yes | Choose the company, or map co from the employee change or paycheck record. Maximum length: 10. |
| `employeeId` | body | `string` | yes | Map id from List Employee Changes or Get Employee. Keep the value exactly as returned, including any leading spaces. Maximum length: 10. |
