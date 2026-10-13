# List Events with Swoogo

## Endpoint

- **Method:** `GET`
- **Path:** `/events`
- **Base URL:** `https://api.swoogo.com/api/v1`
- **Official documentation:** [List Events](https://swoogo.readme.io/reference/getallevents)

## Capabilities

This operation supports [pagination](../README.md#pagination) and [sorting](../README.md#sorting).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `search` | query | `string` | no | Swoogo search conditions, for example status=live or name=*conference*. |
| `ids` | query | `number` | no | Retrieve only these positive event IDs; maximum 100 IDs. Send multiple values as a string separated by `,`. |
| `fields` | query | `string` | no | Fields to return. If omitted, Swoogo returns event ID and name. Send multiple values as a string separated by `,`. |
| `expand` | query | `list<string>` | no | Include the event folder or location. Accepted values: `folder`, `location`. Send multiple values as a string separated by `,`. |
