# ShipBob: List Inventory Levels by Location



```
GET https://connect.mindcloud.co/v1/universal/shipbob/latest/actions/list-inventory-levels-by-location
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ShipBob `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/shipbob/latest/actions/list-inventory-levels-by-location?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/shipbob/latest/actions/list-inventory-levels-by-location?${params}`, {
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`
  }
});

const { success, data } = await response.json();
```



## Response

```json
{
  "success": true,
  "data": [
    {
      "inventoryId": 1,
      "locations": [
        {
          "awaitingQuantity": 1,
          "committedQuantity": 1,
          "damagedQuantity": 1,
          "fulfillableQuantity": 1,
          "internalTransferQuantity": 1,
          "locationId": 1,
          "name": "Ava Chen",
          "onHandQuantity": 1,
          "quarantineQuantity": 1
        }
      ],
      "name": "Ava Chen",
      "sku": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `inventoryId` | number |  |
| `locations` | array<object> |  |
| `locations[].awaitingQuantity` | number |  |
| `locations[].committedQuantity` | number |  |
| `locations[].damagedQuantity` | number |  |
| `locations[].fulfillableQuantity` | number |  |
| `locations[].internalTransferQuantity` | number |  |
| `locations[].locationId` | number |  |
| `locations[].name` | string |  |
| `locations[].onHandQuantity` | number |  |
| `locations[].quarantineQuantity` | number |  |
| `name` | string |  |
| `sku` | string |  |

## Native endpoint

Through the native ShipBob API, this operation is `GET 2026-07/inventory-level/locations?` (base URL `https://{{credentials.apiSubdomain}}.shipbob.com/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-inventory-levels-by-location.md) for the provider-specific parameters and requirements.

