# Create Post with X

## Endpoint

- **Method:** `POST`
- **Path:** `/2/tweets`
- **Base URL:** `https://api.x.com`
- **Official documentation:** [Create Post](https://docs.x.com/x-api/posts/create-post)

## Headers

Send these additional headers for this operation:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/json` |

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `text` | body | `string` | no | Text of the post. Required unless media is supplied; leave empty for a media-only post. Maximum length: 280. |
| `media` | body | `object` | no | — |
| `media.media_ids[]` | body | `array<string>` | no | Uploaded media IDs. Required when Media is provided. Up to four images, one GIF, or one video. |
| `media.tagged_user_ids[]` | body | `array<string>` | no | Up to ten user IDs to tag. |
| `media.title` | body | `string` | no | — |
| `media.description` | body | `string` | no | — |
| `media.preview_media_id` | body | `string` | no | Uploaded media used as the preview image. |
| `media.embeddable` | body | `boolean` | no | — |
| `media.call_to_actions` | body | `object` | no | Call-to-action buttons on attached media. |
| `media.call_to_actions.visit_site` | body | `object` | no | Visit Site call to action. |
| `media.call_to_actions.visit_site.url` | body | `string` | no | HTTPS destination URL. Required when Visit Site is supplied. |
| `media.call_to_actions.watch_now` | body | `object` | no | Watch Now call to action. |
| `media.call_to_actions.watch_now.url` | body | `string` | no | HTTPS destination URL. Required when Watch Now is supplied. |
| `media.call_to_actions.app_install` | body | `object` | no | Provide at least one store ID. |
| `media.call_to_actions.app_install.app_store_id` | body | `string` | no | Apple App Store iPhone app ID. |
| `media.call_to_actions.app_install.ipad_app_store_id` | body | `string` | no | Apple App Store iPad app ID. |
| `media.call_to_actions.app_install.play_store_id` | body | `string` | no | Google Play Store app ID. |
| `reply` | body | `object` | no | — |
| `reply.in_reply_to_tweet_id` | body | `string` | no | Post to reply to. Required when Reply is supplied. |
| `reply.exclude_reply_user_ids[]` | body | `array<string>` | no | Users to exclude from the reply thread. |
| `poll` | body | `object` | no | — |
| `poll.options[]` | body | `array<string>` | no | Two to four choices, each 1–25 characters. Required when Poll is supplied. |
| `poll.duration_minutes` | body | `number` | no | Poll duration, 5–10080 minutes. Required when Poll is supplied. |
| `community_id` | body | `string` | no | Community where the post is created. |
| `reply_settings` | body | `list<string>` | no | Who can reply. Accepted values: `following`, `mentionedUsers`, `subscribers`, `verified`. |
| `made_with_ai` | body | `boolean` | no | Disclose AI-generated media. |
| `paid_partnership` | body | `boolean` | no | Disclose a paid partnership. |
| `quote_tweet_id` | body | `string` | no | Post to quote. Requires X Enterprise API access. |
| `edit_options` | body | `object` | no | Edit an existing post instead of creating a new one. |
| `edit_options.previous_post_id` | body | `string` | no | Post being edited. Required when Edit Options is supplied. |
| `geo` | body | `object` | no | — |
| `geo.place_id` | body | `string` | no | Place for geo tagging; account must permit geolocation. |
| `for_super_followers_only` | body | `boolean` | no | Restrict the post to subscribers. |
| `share_with_followers` | body | `boolean` | no | Share an exclusive post with all followers. |
| `card_uri` | body | `string` | no | Card URI parameter. |
| `direct_message_deep_link` | body | `string` | no | Direct message deep link. |
| `nullcast` | body | `boolean` | no | Do not display this post in the public timeline. |
