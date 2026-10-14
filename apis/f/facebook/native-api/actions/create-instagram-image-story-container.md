# Create Instagram Image Story Container with Facebook

## Endpoint

- **Method:** `POST`
- **Path:** `https://graph.facebook.com/v26.0/:instagramAccountId/media`
- **Base URL:** `https://graph.facebook.com/v25.0`
- **Official documentation:** [Create Instagram Image Story Container](https://developers.facebook.com/documentation/instagram-platform/instagram-graph-api/reference/ig-user/media)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `instagramAccountId` | path | `string` | yes | Professional Instagram account ID linked to your Facebook Page. Use Get Page with instagram_business_account to discover it. |
| `image_url` | query | `string` | yes | Public JPEG URL for an image Story; supply image URL or video URL. |
