# List Product Groups with Epicor Prophet 21

## Endpoint

- **Method:** `GET`
- **Path:** `/data/erp/views/v1/p21_view_product_group`
- **Base URL:** `{apiUrl}`

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `$select` | query | `string` | no | Comma-separated field names. Leave empty to return all available fields. |
| `$filter` | query | `string` | no | A Prophet 21 filter expression, such as customer_id eq 123. |
