# Create Instagram Image Container with Facebook

## Endpoint

- **Method:** `POST`
- **Path:** `https://graph.facebook.com/v26.0/:instagramAccountId/media`
- **Base URL:** `https://graph.facebook.com/v25.0`
- **Official documentation:** [Create Instagram Image Container](https://developers.facebook.com/documentation/instagram-platform/instagram-graph-api/reference/ig-user/media)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `instagramAccountId` | path | `string` | yes | Professional Instagram account ID linked to your Facebook Page. Use Get Page with instagram_business_account to discover it. |
| `image_url` | query | `string` | yes | Public JPEG URL. Maximum 8 MB; aspect ratio 4:5 to 1.91:1. |
| `caption` | query | `string` | no | Caption with hashtags and mentions. Omit for carousel children. Maximum length: 2200. |
| `alt_text` | query | `string` | no | Maximum length: 1000. |
| `is_carousel_item` | query | `boolean` | no | — |
| `is_ai_generated` | query | `boolean` | no | Do not set on carousel children; set on the carousel parent. |
| `location_id` | query | `string` | no | — |
| `is_paid_partnership` | query | `boolean` | no | — |
