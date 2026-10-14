# Create Post with LinkedIn

Creates a new post in LinkedIn.

## Endpoint

- **Method:** `POST`
- **Path:** `/rest/posts`
- **Base URL:** `https://api.linkedin.com`
- **Official documentation:** [Create Post](https://learn.microsoft.com/en-us/linkedin/marketing/community-management/shares/posts-api?view=li-lms-2025-11)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `adContext.dscName` | body | `string` | no | — |
| `author` | body | `string` | yes | Author URN such as urn:li:organization:{id} or urn:li:person:{id}. |
| `content.article.source` | body | `string` | no | — |
| `content.media` | body | `object` | no | — |
| `content.media.id` | body | `string` | no | Uploaded image, video, or document URN. |
| `content.multiImage.altText` | body | `string` | no | — |
| `content.multiImage.images[].id` | body | `string` | no | — |
| `content.poll.options[].text` | body | `string` | no | Maximum 30 characters. |
| `content.poll.question` | body | `string` | no | Maximum 140 characters. |
| `content.poll.settings.duration` | body | `list<string>` | no | ONE_DAY, THREE_DAYS, SEVEN_DAYS, or FOURTEEN_DAYS. Accepted values: `FOURTEEN_DAYS`, `ONE_DAY`, `SEVEN_DAYS`, `THREE_DAYS`. |
| `distribution.feedDistribution` | body | `list<string>` | yes | Feed distribution mode for this post. Accepted values: `MAIN_FEED`, `NONE`. |
| `distribution.targetEntities[].degrees[]` | body | `array<string>` | no | — |
| `distribution.targetEntities[].interfaceLocales[].country` | body | `string` | no | — |
| `reshareContext.parent` | body | `string` | no | URN of the original post to reshare. |
| `adContext.dscStatus` | body | `list<string>` | no | Accepted values: `ACTIVE`, `ARCHIVED`. |
| `commentary` | body | `string` | yes | Text content for the post commentary. |
| `content.article` | body | `object` | no | — |
| `content.article.title` | body | `string` | no | — |
| `content.media.title` | body | `string` | no | Required when posting a document. |
| `content.multiImage.images[]` | body | `array<object>` | no | Include 2–20 uploaded image assets owned by the post author. |
| `content.multiImage.images[].title` | body | `string` | no | — |
| `content.poll.options[]` | body | `array<object>` | no | Provide 2–4 options. |
| `content.poll.settings.voteSelectionType` | body | `list<string>` | no | Only SINGLE_VOTE is currently supported. Accepted values: `SINGLE_VOTE`. |
| `distribution.targetEntities[]` | body | `array<object>` | no | Organization follower targeting requires an audience of more than 300 members. |
| `distribution.targetEntities[].fieldsOfStudy[]` | body | `array<string>` | no | — |
| `distribution.targetEntities[].interfaceLocales[].language` | body | `string` | no | — |
| `content.article.thumbnail` | body | `string` | no | — |
| `content.media.altText` | body | `string` | no | — |
| `content.multiImage` | body | `object` | no | — |
| `content.multiImage.images[].altText` | body | `string` | no | — |
| `content.poll.settings` | body | `object` | no | — |
| `content.poll.settings.isVoterVisibleToAuthor` | body | `boolean` | no | Only true is currently supported. |
| `distribution.targetEntities[].geoLocations[]` | body | `array<string>` | no | — |
| `distribution.thirdPartyDistributionChannels[]` | body | `array<string>` | no | — |
| `visibility` | body | `list<string>` | no | Who can see the post. Accepted values: `CONNECTIONS`, `CONTAINER`, `LOGGED_IN`, `PUBLIC`. |
| `content` | body | `object` | no | Choose one content type. Omit for a text-only post. |
| `content.article.thumbnailAltText` | body | `string` | no | — |
| `content.poll` | body | `object` | no | Organic posts only. |
| `distribution.targetEntities[].industries[]` | body | `array<string>` | no | — |
| `content.article.description` | body | `string` | no | — |
| `distribution.targetEntities[].interfaceLocales[]` | body | `array<object>` | no | — |
| `reshareContext` | body | `object` | no | — |
| `distribution.targetEntities[].jobFunctions[]` | body | `array<string>` | no | — |
| `isReshareDisabledByAuthor` | body | `boolean` | no | — |
| `distribution` | body | `object` | yes | Distribution settings container. |
| `distribution.targetEntities[].organizations[]` | body | `array<string>` | no | — |
| `container` | body | `string` | no | — |
| `distribution.targetEntities[].seniorities[]` | body | `array<string>` | no | — |
| `contentLandingPage` | body | `string` | no | — |
| `distribution.targetEntities[].staffCountRanges[]` | body | `array<string>` | no | — |
| `contentCallToActionLabel` | body | `list<string>` | no | Accepted values: `APPLY`, `ATTEND`, `BUY_NOW`, `DOWNLOAD`, `JOIN`, `LEARN_MORE`, `REGISTER`, `REQUEST_DEMO`, `SEE_MORE`, `SHOP_NOW`, `SIGN_UP`, `SUBSCRIBE`, `VIEW_QUOTE`. |
| `adContext` | body | `object` | no | — |
