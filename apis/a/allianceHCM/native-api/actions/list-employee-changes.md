# List Employee Changes with Alliance HCM

## Endpoint

- **Method:** `POST`
- **Path:** `/load`
- **Base URL:** `https://api2.hralliance.net/AllPayRestData.svc/json`
- **Official documentation:** [List Employee Changes](https://api2.hralliance.net/JSONAPIManual.html#Load)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `companyCode` | body | `list<string>` | yes | — |
| `previousCheckpoint` | body | `string` | yes | Return changes after this date and time. For your first run, enter when you want to start. For later runs, use the End Date from the last fully completed run. Use Alliance's date/time format, for example 2026-10-01T00:00:00. |
| `currentCheckpoint` | body | `string` | yes | Return changes up to and including this date and time. Run Get Employee Change Log Sync Time for the same company and use its returned date/time exactly as provided. This is the latest time Alliance has finished processing, helping avoid missing delayed changes. After processing all pages, save this value as the next Start Date. |
| `employeeId` | body | `string` | no | Optional. Map id from an employee or change record; leave empty for all employees in the chosen company. Maximum length: 10. |
| `changeType` | body | `list<string>` | no | Accepted values: `D`, `I`, `U`. |
