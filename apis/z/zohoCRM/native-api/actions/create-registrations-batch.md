# Create Registrations with Zoho CRM

## Endpoint

- **Method:** `POST`
- **Path:** `/Registrations`
- **Base URL:** `{api_domain}/crm/v8`
- **Official documentation:** [Create Registrations](https://www.zoho.com/crm/developer/docs/api/v7/insert-records.html)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `data[]` | body | `array<object>` | yes | Zoho CRM records to create. Each array item is sent as one record. |
