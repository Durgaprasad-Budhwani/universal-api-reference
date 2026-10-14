# Publish Instagram Media with Facebook

## Endpoint

- **Method:** `POST`
- **Path:** `https://graph.facebook.com/v26.0/:instagramAccountId/media_publish`
- **Base URL:** `https://graph.facebook.com/v25.0`
- **Official documentation:** [Publish Instagram Media](https://developers.facebook.com/documentation/instagram-platform/instagram-graph-api/reference/ig-user/media_publish)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `instagramAccountId` | path | `string` | yes | Professional Instagram account ID linked to your Facebook Page. Use Get Page with instagram_business_account to discover it. |
| `creation_id` | query | `string` | yes | Container ID to publish. For video, check that container status is FINISHED first. |
