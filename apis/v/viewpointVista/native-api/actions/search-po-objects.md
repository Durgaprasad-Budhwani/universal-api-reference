# Search PO Objects with Viewpoint Vista

Search objects found in Viewpoint® Vista™ Search (PO) programs.

## Endpoint

- **Method:** `POST`
- **Path:** `v1/direct/subscribers/:subscriber_code/vista/:api/2/data/:object/cache/search`
- **Base URL:** `https://api.xchange.trimble.com/connect/`
- **API:** REST
- **Official documentation:** [Search PO Objects](https://direct-api.xchange.trimble.com/reference/get-directsubscriberssubscriber_codevistasm2datacustomerscache)

## Capabilities

This operation supports [filtering](../README.md#filtering).

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `modifiedUtcAfter` | body | `date` | no | — |
| `object` | path | `list<string>` | yes | Specify the type of Object from the Purchase Order V2 Direct API that you'd like to retrieve. Accepted values: `category_discounts`, `change_orders`, `co_batch_entries`, `co_batches`, `company_parameters`, `compliances`, `pending_po_headers`, `pending_po_lines`, `po_batch_entries`, `po_batches`, `po_distributions`, `po_headers`, `po_lines`, `purchase_orders`, `receipt_bat_entries`, `receipt_batches`, `receipts`, `shipping_locations`, `vendor_materials`. |
| `modifiedUtcBefore` | body | `date` | no | — |
