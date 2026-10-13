# List Registrants with Swoogo

## Endpoint

- **Method:** `GET`
- **Path:** `/registrants`
- **Base URL:** `https://api.swoogo.com/api/v1`
- **Official documentation:** [List Registrants](https://swoogo.readme.io/reference/getallregistrants)

## Capabilities

This operation supports [pagination](../README.md#pagination) and [sorting](../README.md#sorting).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `event_id` | query | `list<number>` | yes | The event whose registrants you want to list. |
| `search` | query | `string` | no | Swoogo search conditions, for example registration_status=confirmed or email=*@example.com*. |
| `ids` | query | `number` | no | Retrieve only these positive registrant IDs; maximum 100 IDs. Send multiple values as a string separated by `,`. |
| `fields` | query | `string` | no | Fields to return. If omitted, Swoogo returns ID, first name, and last name. Send multiple values as a string separated by `,`. |
| `expand` | query | `list<string>` | no | Include related address objects. Accepted values: `billingAddress`, `homeAddress`, `workAddress`. Send multiple values as a string separated by `,`. |
