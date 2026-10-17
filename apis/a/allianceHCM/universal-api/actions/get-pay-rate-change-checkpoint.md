# Alliance HCM: Get Pay Rate Change Checkpoint



```
GET https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-pay-rate-change-checkpoint
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Alliance HCM `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-pay-rate-change-checkpoint?connectionId=$CONNECTION_ID&companyCode=string" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  "companyCode": "string"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/allianceHCM/latest/actions/get-pay-rate-change-checkpoint?${params}`, {
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
| `companyCode` | list<string> | yes |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "response": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `response` | string | Alliance server-time checkpoint. Keep this text unchanged when mapping it into Previous Checkpoint or Current Checkpoint. |

## Native endpoint

Through the native Alliance HCM API, this operation is `POST /getlastchangetime` (base URL `https://api2.hralliance.net/AllPayRestData.svc/json`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/get-pay-rate-change-checkpoint.md) for the provider-specific parameters and requirements.

