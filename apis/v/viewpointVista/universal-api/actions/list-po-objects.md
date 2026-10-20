# Viewpoint Vista: List PO Objects

Represents data found in Viewpoint® Vista™ PO programs.

```
GET https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-po-objects
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Viewpoint Vista `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-po-objects?connectionId=$CONNECTION_ID&object=category_discounts" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "object": "category_discounts"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/list-po-objects?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as query string parameters ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `modifiedUTCSince` | string | no | Specify a datetime against which to filter the results. When specified the result will be ordered oldest __modifiedUTC to newest. Example `2019-12-11T20:16:58.3419275Z`. ( Optional ) If unspecified, all cached objects will be returned. |
| `object` | list<string> | yes | Specify the type of Object from the Purchase Order V2 Direct API that you'd like to retrieve. One of: `category_discounts`, `change_orders`, `co_batch_entries`, `co_batches`, `company_parameters`, `compliances`, `pending_po_headers`, `pending_po_lines`, `po_batch_entries`, `po_batches`, `po_distributions`, `po_headers`, `po_lines`, `purchase_orders`, `receipt_bat_entries`, `receipt_batches`, `receipts`, `shipping_locations`, `vendor_materials`. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native Viewpoint Vista API returns.

## Native endpoint

Through the native Viewpoint Vista API, this operation is `GET v1/direct/subscribers/:subscriber_code/vista/:api/2/data/:object/cache` (base URL `https://api.xchange.trimble.com/connect/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/list-po-objects.md) for the provider-specific parameters and requirements.

