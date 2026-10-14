# Get Instagram Container Status with Facebook

## Endpoint

- **Method:** `GET`
- **Path:** `https://graph.facebook.com/v26.0/:containerId`
- **Base URL:** `https://graph.facebook.com/v25.0`
- **Official documentation:** [Get Instagram Container Status](https://developers.facebook.com/documentation/instagram-platform/instagram-graph-api/reference/ig-container)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `containerId` | path | `string` | yes | — |
| `fields` | query | `list<string>` | no | Accepted values: `copyright_check_status`, `id`, `status`, `status_code`. Send multiple values as a string separated by `,`. |
