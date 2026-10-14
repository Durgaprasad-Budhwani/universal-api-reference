# X: Create Post



```
POST https://connect.mindcloud.co/v1/universal/x/latest/actions/create-post
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a X `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/x/latest/actions/create-post" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID"
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/x/latest/actions/create-post', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `text` | string | no | Text of the post. Required unless media is supplied; leave empty for a media-only post. |
| `media` | object | no |  |
| `media.mediaIds[]` | array<string> | no | Uploaded media IDs. Required when Media is provided. Up to four images, one GIF, or one video. |
| `reply` | object | no |  |
| `reply.inReplyToTweetId` | string | no | Post to reply to. Required when Reply is supplied. |
| `poll` | object | no |  |
| `poll.options[]` | array<string> | no | Two to four choices, each 1–25 characters. Required when Poll is supplied. |
| `poll.durationMinutes` | number | no | Poll duration, 5–10080 minutes. Required when Poll is supplied. |
| `communityId` | string | no | Community where the post is created. |
| `madeWithAi` | boolean | no | Disclose AI-generated media. |
| `paidPartnership` | boolean | no | Disclose a paid partnership. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `media.taggedUserIds[]` | array<string> | no | Up to ten user IDs to tag. |
| `media.title` | string | no |  |
| `media.description` | string | no |  |
| `media.previewMediaId` | string | no | Uploaded media used as the preview image. |
| `media.embeddable` | boolean | no |  |
| `media.callToActions` | object | no | Call-to-action buttons on attached media. |
| `media.callToActions.visitSite` | object | no | Visit Site call to action. |
| `media.callToActions.visitSite.url` | string | no | HTTPS destination URL. Required when Visit Site is supplied. |
| `media.callToActions.watchNow` | object | no | Watch Now call to action. |
| `media.callToActions.watchNow.url` | string | no | HTTPS destination URL. Required when Watch Now is supplied. |
| `media.callToActions.appInstall` | object | no | Provide at least one store ID. |
| `media.callToActions.appInstall.appStoreId` | string | no | Apple App Store iPhone app ID. |
| `media.callToActions.appInstall.ipadAppStoreId` | string | no | Apple App Store iPad app ID. |
| `media.callToActions.appInstall.playStoreId` | string | no | Google Play Store app ID. |
| `reply.excludeReplyUserIds[]` | array<string> | no | Users to exclude from the reply thread. |
| `replySettings` | list<string> | no | Who can reply. One of: `following`, `mentionedUsers`, `subscribers`, `verified`. |
| `quoteTweetId` | string | no | Post to quote. Requires X Enterprise API access. |
| `editOptions` | object | no | Edit an existing post instead of creating a new one. |
| `editOptions.previousPostId` | string | no | Post being edited. Required when Edit Options is supplied. |
| `geo` | object | no |  |
| `geo.placeId` | string | no | Place for geo tagging; account must permit geolocation. |
| `forSuperFollowersOnly` | boolean | no | Restrict the post to subscribers. |
| `shareWithFollowers` | boolean | no | Share an exclusive post with all followers. |
| `cardUri` | string | no | Card URI parameter. |
| `directMessageDeepLink` | string | no | Direct message deep link. |
| `nullcast` | boolean | no | Do not display this post in the public timeline. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native X API returns.

## Native endpoint

Through the native X API, this operation is `POST /2/tweets` (base URL `https://api.x.com`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/create-post.md) for the provider-specific parameters and requirements.

