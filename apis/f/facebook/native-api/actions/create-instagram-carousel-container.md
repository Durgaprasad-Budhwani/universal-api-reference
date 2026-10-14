# Create Instagram Carousel Container with Facebook

## Endpoint

- **Method:** `POST`
- **Path:** `https://graph.facebook.com/v26.0/:instagramAccountId/media`
- **Base URL:** `https://graph.facebook.com/v25.0`
- **Official documentation:** [Create Instagram Carousel Container](https://developers.facebook.com/documentation/instagram-platform/instagram-graph-api/reference/ig-user/media)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `instagramAccountId` | path | `string` | yes | Professional Instagram account ID linked to your Facebook Page. Use Get Page with instagram_business_account to discover it. |
| `children` | query | `string` | yes | Up to 10 image/video container IDs in display order. Create children first; Reels are not supported. Send multiple values as a string separated by `,`. |
| `caption` | query | `string` | no | Maximum length: 2200. |
| `location_id` | query | `string` | no | — |
| `is_ai_generated` | query | `boolean` | no | — |
| `is_paid_partnership` | query | `boolean` | no | — |
