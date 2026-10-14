# Get Instagram Publishing Limit with Facebook

## Endpoint

- **Method:** `GET`
- **Path:** `https://graph.facebook.com/v26.0/:instagramAccountId/content_publishing_limit`
- **Base URL:** `https://graph.facebook.com/v25.0`
- **Official documentation:** [Get Instagram Publishing Limit](https://developers.facebook.com/documentation/instagram-platform/instagram-graph-api/reference/ig-user/content_publishing_limit)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `instagramAccountId` | path | `string` | yes | Professional Instagram account ID linked to your Facebook Page. Use Get Page with instagram_business_account to discover it. |
| `fields` | query | `list<string>` | no | Accepted values: `config`, `quota_usage`. Send multiple values as a string separated by `,`. |
