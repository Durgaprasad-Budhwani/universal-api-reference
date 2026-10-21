# Get Sales Accrual Report with Zenoti

## Endpoint

- **Method:** `POST`
- **Path:** `reports/sales/accrual_basis/flat_file`
- **Base URL:** `https://api.zenoti.com/v1/`
- **Official documentation:** [Get Sales Accrual Report](None)

## Capabilities

This operation supports [pagination](../README.md#pagination).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `center_ids[].center` | body | `list` | no | — |
| `invoice_statuses[].invoiceStatus` | body | `list` | no | Accepted values: `0`, `4`. |
| `item_types[].itemType` | body | `list` | no | Accepted values: `DayPromoPackage`, `GiftCard`, `Membership`, `OtherFees`, `Package`, `PrepaidCard`, `Product`, `Service`. |
| `payment_types[].paymentType` | body | `list` | no | Accepted values: `0`, `1`, `10`, `16`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`. |
| `sale_types[].saleType` | body | `list` | no | Accepted values: `0`, `1`, `2`, `3`. |
| `start_date` | body | `date` | yes | — |
| `end_date` | body | `date` | yes | — |
| `center_ids[]` | body | `array` | no | — |
| `item_types[]` | body | `array` | no | — |
| `payment_types[]` | body | `array` | no | — |
| `sale_types[]` | body | `array` | no | — |
| `invoice_statuses[]` | body | `array` | no | — |
| `includeTotal` | body | `boolean` | no | Format: `toggle`. |
