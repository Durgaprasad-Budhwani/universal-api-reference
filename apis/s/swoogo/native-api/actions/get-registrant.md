# Get Registrant with Swoogo

## Endpoint

- **Method:** `GET`
- **Path:** `/registrants/:registrant_id`
- **Base URL:** `https://api.swoogo.com/api/v1`
- **Official documentation:** [Get Registrant](https://swoogo.readme.io/reference/getoneregistrant)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `registrant_id` | path | `number` | yes | — |
| `fields` | query | `string` | no | — |
| `expand` | query | `string` | no | Comma-separated related objects: homeAddress, workAddress, billingAddress. |
