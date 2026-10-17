# Get Employee with Alliance HCM

## Endpoint

- **Method:** `POST`
- **Path:** `/load`
- **Base URL:** `https://api2.hralliance.net/AllPayRestData.svc/json`
- **Official documentation:** [Get Employee](https://api2.hralliance.net/JSONAPIManual.html#Load)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `companyCode` | body | `list<string>` | yes | Choose the company, or map co from List Employee Changes. Employee IDs are specific to a company. Maximum length: 10. |
| `employeeId` | body | `string` | yes | Map id from List Employee Changes or List Employees. Use the value exactly as returned, including any leading spaces. Maximum length: 10. |
