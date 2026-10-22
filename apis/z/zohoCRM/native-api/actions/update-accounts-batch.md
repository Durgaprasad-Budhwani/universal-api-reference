# Update Accounts with Zoho CRM

## Endpoint

- **Method:** `PUT`
- **Path:** `/Accounts`
- **Base URL:** `{api_domain}/crm/v8`
- **Official documentation:** [Update Accounts](https://www.zoho.com/crm/developer/docs/api/v7/update-records.html)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `data[]` | body | `array<object>` | yes | Zoho CRM records to update. Each array item is sent as one record. |
