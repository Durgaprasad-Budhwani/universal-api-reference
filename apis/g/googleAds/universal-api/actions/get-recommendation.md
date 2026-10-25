# Google Ads: Get Recommendation

Retrieves a recommendation from Google Ads.

```
GET https://connect.mindcloud.co/v1/universal/googleAds/latest/actions/get-recommendation
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Google Ads `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/googleAds/latest/actions/get-recommendation?connectionId=$CONNECTION_ID&customerId=1234567890&query=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "customerId": "1234567890",
  "query": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/googleAds/latest/actions/get-recommendation?${params}`, {
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
| `customerId` | list | yes | Customer ID to query (without dashes). Example: `1234567890`. |
| `query` | string | yes | GAQL query used to fetch a single recommendation resource. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "recommendation": {
        "resourceName": "Ava Chen",
        "type": "string"
      }
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `recommendation.resourceName` | string |  |
| `recommendation.type` | string |  |

## Native endpoint

Through the native Google Ads API, this operation is `POST v23/customers/:customerId/googleAds:search` (base URL `https://googleads.googleapis.com/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-recommendation.md) for the provider-specific parameters and requirements.

