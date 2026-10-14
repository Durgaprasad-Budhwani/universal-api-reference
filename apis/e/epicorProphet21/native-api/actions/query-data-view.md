# Query Data View with Epicor Prophet 21

## Endpoint

- **Method:** `GET`
- **Path:** `/data/erp/views/v1/{{view}}`
- **Base URL:** `{apiUrl}`

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `view` | path | `string` | yes | The Prophet 21 data view name, such as p21_view_customer. |
| `$select` | query | `string` | no | Comma-separated field names. Leave empty to return all available fields. |
| `$filter` | query | `string` | no | A Prophet 21 filter expression, such as customer_id eq 123. |
