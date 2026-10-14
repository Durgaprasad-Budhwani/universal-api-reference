# LinkedIn: Create Post

Creates a new post in LinkedIn.

```
POST https://connect.mindcloud.co/v1/universal/linkedin/latest/actions/create-post
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a LinkedIn `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/linkedin/latest/actions/create-post" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "author": "urn:li:organization:5515715",
  "distribution.feedDistribution": "MAIN_FEED",
  "commentary": "Sample text post created from LinkedIn API",
  "distribution": {}
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/linkedin/latest/actions/create-post', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "author": "urn:li:organization:5515715",
    "distribution.feedDistribution": "MAIN_FEED",
    "commentary": "Sample text post created from LinkedIn API",
    "distribution": {}
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `adContext.dscName` | string | no |  |
| `author` | string | yes | Author URN such as urn:li:organization:{id} or urn:li:person:{id}. Example: `urn:li:organization:5515715`. |
| `content.article.source` | string | no |  |
| `content.media` | object | no |  |
| `content.media.id` | string | no | Uploaded image, video, or document URN. |
| `content.multiImage.altText` | string | no |  |
| `content.multiImage.images[].id` | string | no |  |
| `content.poll.options[].text` | string | no | Maximum 30 characters. |
| `content.poll.question` | string | no | Maximum 140 characters. |
| `content.poll.settings.duration` | list<string> | no | ONE_DAY, THREE_DAYS, SEVEN_DAYS, or FOURTEEN_DAYS. One of: `FOURTEEN_DAYS`, `ONE_DAY`, `SEVEN_DAYS`, `THREE_DAYS`. |
| `distribution.feedDistribution` | list<string> | yes | Feed distribution mode for this post. One of: `MAIN_FEED`, `NONE`. Default: `MAIN_FEED`. |
| `distribution.targetEntities[].degrees[]` | array<string> | no |  |
| `distribution.targetEntities[].interfaceLocales[].country` | string | no |  |
| `reshareContext.parent` | string | no | URN of the original post to reshare. |
| `adContext.dscStatus` | list<string> | no | One of: `ACTIVE`, `ARCHIVED`. |
| `commentary` | string | yes | Text content for the post commentary. Example: `Sample text post created from LinkedIn API`. |
| `content.article` | object | no |  |
| `content.article.title` | string | no |  |
| `content.media.title` | string | no | Required when posting a document. |
| `content.multiImage.images[]` | array<object> | no | Include 2–20 uploaded image assets owned by the post author. |
| `content.multiImage.images[].title` | string | no |  |
| `content.poll.options[]` | array<object> | no | Provide 2–4 options. |
| `content.poll.settings.voteSelectionType` | list<string> | no | Only SINGLE_VOTE is currently supported. One of: `SINGLE_VOTE`. |
| `distribution.targetEntities[]` | array<object> | no | Organization follower targeting requires an audience of more than 300 members. |
| `distribution.targetEntities[].fieldsOfStudy[]` | array<string> | no |  |
| `distribution.targetEntities[].interfaceLocales[].language` | string | no |  |
| `content.article.thumbnail` | string | no |  |
| `content.media.altText` | string | no |  |
| `content.multiImage` | object | no |  |
| `content.multiImage.images[].altText` | string | no |  |
| `content.poll.settings` | object | no |  |
| `content.poll.settings.isVoterVisibleToAuthor` | boolean | no | Only true is currently supported. |
| `distribution.targetEntities[].geoLocations[]` | array<string> | no |  |
| `distribution.thirdPartyDistributionChannels[]` | array<string> | no |  |
| `visibility` | list<string> | no | Who can see the post. One of: `CONNECTIONS`, `CONTAINER`, `LOGGED_IN`, `PUBLIC`. Default: `PUBLIC`. Example: `PUBLIC`. |
| `content` | object | no | Choose one content type. Omit for a text-only post. |
| `content.article.thumbnailAltText` | string | no |  |
| `content.poll` | object | no | Organic posts only. |
| `distribution.targetEntities[].industries[]` | array<string> | no |  |
| `content.article.description` | string | no |  |
| `distribution.targetEntities[].interfaceLocales[]` | array<object> | no |  |
| `reshareContext` | object | no |  |
| `distribution.targetEntities[].jobFunctions[]` | array<string> | no |  |
| `isReshareDisabledByAuthor` | boolean | no |  |
| `distribution` | object | yes | Distribution settings container. |
| `distribution.targetEntities[].organizations[]` | array<string> | no |  |
| `container` | string | no |  |
| `distribution.targetEntities[].seniorities[]` | array<string> | no |  |
| `contentLandingPage` | string | no |  |
| `distribution.targetEntities[].staffCountRanges[]` | array<string> | no |  |
| `contentCallToActionLabel` | list<string> | no | One of: `APPLY`, `ATTEND`, `BUY_NOW`, `DOWNLOAD`, `JOIN`, `LEARN_MORE`, `REGISTER`, `REQUEST_DEMO`, `SEE_MORE`, `SHOP_NOW`, `SIGN_UP`, `SUBSCRIBE`, `VIEW_QUOTE`. |
| `adContext` | object | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "value": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `value` | string | LinkedIn returns the created post identifier in the x-restli-id response header and no response body for this successful mutation. |

## Native endpoint

Through the native LinkedIn API, this operation is `POST /rest/posts` (base URL `https://api.linkedin.com`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/create-post.md) for the provider-specific parameters and requirements.

