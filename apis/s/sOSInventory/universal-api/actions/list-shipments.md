# SOS Inventory: List Shipments

Retrieves shipments from SOS Inventory.

```
GET https://connect.mindcloud.co/v1/universal/sOSInventory/latest/actions/list-shipments
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a SOS Inventory `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/sOSInventory/latest/actions/list-shipments?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/sOSInventory/latest/actions/list-shipments?${params}`, {
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
| `archived` | string | no | Use yes to return archived records only or no to return active records only. |
| `email` | string | no | Filter by the customer's email. |
| `name` | string | no | Filter by matches on the name or fullname fields. |
| `query` | string | no | Filter by matches on name, fullname, or notes. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "archived": true,
      "assignedToUser": {},
      "billing": {
        "address": "string",
        "addressName": "Ava Chen",
        "addressType": "string",
        "company": "string",
        "contact": "string",
        "email": "ava@example.com",
        "phone": "string"
      },
      "channel": {
        "id": 1,
        "name": "Ava Chen"
      },
      "comment": "string",
      "createBillForShippingAmount": true,
      "customer": {
        "fullname": "Ava Chen",
        "id": 1,
        "name": "Ava Chen"
      },
      "customerMessage": {},
      "customerNotes": {},
      "customerPO": "string",
      "customFields": {},
      "date": "string",
      "department": {},
      "forceToShipStation": true,
      "hasSignature": true,
      "id": 1,
      "keys": {},
      "lines": [
        {}
      ],
      "linkedTransaction": {},
      "location": {
        "id": 1,
        "name": "Ava Chen"
      },
      "number": "string",
      "priority": {},
      "shipBy": "string",
      "shipping": {
        "address": "string",
        "addressName": "Ava Chen",
        "addressType": "string",
        "company": "string",
        "contact": "string",
        "email": "ava@example.com",
        "phone": "string"
      },
      "shippingAmount": 1,
      "shippingMethod": {
        "id": 1,
        "name": "Ava Chen"
      },
      "starred": 1,
      "summaryOnly": true,
      "syncToken": 1,
      "total": 1,
      "trackingLink": "https://example.com",
      "trackingNumber": "string",
      "values": {}
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `archived` | boolean |  |
| `assignedToUser` | object |  |
| `billing.address` | string |  |
| `billing.addressName` | string |  |
| `billing.addressType` | string |  |
| `billing.company` | string |  |
| `billing.contact` | string |  |
| `billing.email` | string |  |
| `billing.phone` | string |  |
| `channel.id` | number |  |
| `channel.name` | string |  |
| `comment` | string |  |
| `createBillForShippingAmount` | boolean |  |
| `customer.fullname` | string |  |
| `customer.id` | number |  |
| `customer.name` | string |  |
| `customerMessage` | object |  |
| `customerNotes` | object |  |
| `customerPO` | string |  |
| `customFields` | object |  |
| `date` | string |  |
| `department` | object |  |
| `forceToShipStation` | boolean |  |
| `hasSignature` | boolean |  |
| `id` | number |  |
| `keys` | object |  |
| `lines` | array<object> |  |
| `linkedTransaction` | object |  |
| `location.id` | number |  |
| `location.name` | string |  |
| `number` | string |  |
| `priority` | object |  |
| `shipBy` | string |  |
| `shipping.address` | string |  |
| `shipping.addressName` | string |  |
| `shipping.addressType` | string |  |
| `shipping.company` | string |  |
| `shipping.contact` | string |  |
| `shipping.email` | string |  |
| `shipping.phone` | string |  |
| `shippingAmount` | number |  |
| `shippingMethod.id` | number |  |
| `shippingMethod.name` | string |  |
| `starred` | number |  |
| `summaryOnly` | boolean |  |
| `syncToken` | number |  |
| `total` | number |  |
| `trackingLink` | string |  |
| `trackingNumber` | string |  |
| `values` | object |  |

## Native endpoint

Through the native SOS Inventory API, this operation is `GET /api/v2/shipment` (base URL `https://api.sosinventory.com`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-shipments.md) for the provider-specific parameters and requirements.

