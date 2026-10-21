# Get Entity Items with EHS Insight

## Endpoint

- **Method:** `GET`
- **Path:** `/v4/entity/:entityName/list?:customparams`
- **Base URL:** `https://{companyName}.ehsinsight.com/api`

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `entityName` | path | `string` | yes | — |
| `customparams` | query | `string` | no | Optional provider-specific query string segment appended after the list route. |
