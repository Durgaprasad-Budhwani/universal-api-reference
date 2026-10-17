# List Employee Paycheck Line Items with Alliance HCM

## Endpoint

- **Method:** `POST`
- **Path:** `/load`
- **Base URL:** `https://api2.hralliance.net/AllPayRestData.svc/json`
- **Official documentation:** [List Employee Paycheck Line Items](https://api2.hralliance.net/JSONAPIManual.html#Load)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `companyCode` | body | `list<string>` | yes | Choose the company, or map co from the employee change or paycheck record. Maximum length: 10. |
| `paycheckTransactionId` | body | `string` | yes | Map trans from List Employee Pay History. This identifies one processed paycheck. Retrieve pay history using the Employee ID first. Maximum length: 36. |
