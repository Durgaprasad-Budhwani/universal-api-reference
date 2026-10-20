# Apollo: Search for Contacts

Finds contacts in your Apollo account.

```
GET https://connect.mindcloud.co/v1/universal/apolloio/latest/actions/search-for-contacts
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Apollo `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/apolloio/latest/actions/search-for-contacts?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/apolloio/latest/actions/search-for-contacts?${params}`, {
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
| `labelIds` | string<string> | no | Accepts multiple values as an array. |
| `qKeywords` | string | no | Add keywords to narrow the search of the contacts in your team's Apollo account. Keywords can include combinations of names, job titles, employers (company names), and email addresses. Examples: `tim zheng`; `senior research analyst`; `microsoft` Accepts multiple values as an array. |
| `contactStageIds[]` | array<string> | no | The Apollo IDs for the contact stages that you want to include in your search results. If you add multiple contact stages, Apollo will include all contacts that match any of the stages, along with the other parameters, in the search results. Call the [List Contact Stages endpoint](https://docs.apollo.io/reference/list-contact-stages) to retrieve a list of all the contact stage IDs available in your Apollo account. Example: `6095a710bd01d100a506d4ae` |
| `contactLabelIds[]` | array<string> | no | The Apollo IDs for the labels that you want to include in your search results. If you add multiple labels, Apollo will include all contacts connected to any of the labels, along with the other parameters, in the search results. Example: `['6095a710bd01d100a506d4ae']` |
| `contactStage` | list<string> | no | The contact stages that you want to include in your search results. If you add multiple contact stages, Apollo will include all contacts that match any of the stages, along with the other parameters, in the search results. Accepts multiple values as an array. |
| `sortByField` | string | no | Sort the matching contacts by 1 of the following options: - `contact_last_activity_date`: The most recent activity date recorded first. - `contact_email_last_opened_at`: The most recent email opened date first. - `contact_email_last_clicked_at`: The most recent email clicked first. - `contact_created_at`: The most recently created first. - `contact_updated_at`: The most recently updated first. |
| `sortAscending` | boolean | no | Set to `true` to sort the matching contacts in ascending order. This parameter must be used with `sort_by_field`. Otherwise, the sorting logic is not applied. Example: `true` |

## Response

```json
{
  "success": true,
  "data": [
    {
      "account": {},
      "accountId": "string",
      "accountPhoneNote": "string",
      "callOptedOut": true,
      "city": "string",
      "contactCampaignStatuses": [
        {}
      ],
      "contactEmails": [
        {}
      ],
      "contactJobChangeEvent": {},
      "contactRoles": [
        {}
      ],
      "contactStageId": "string",
      "country": "string",
      "createdAt": "2026-05-07T12:00:00.000Z",
      "creatorId": "string",
      "crmId": "string",
      "crmOwnerId": "string",
      "crmRecordUrl": "https://example.com",
      "customFieldErrors": {},
      "directDialEnrichmentFailedAt": "2026-05-07T12:00:00.000Z",
      "directDialStatus": "string",
      "directoryUrl": "https://example.com",
      "email": "ava@example.com",
      "emailDomainCatchall": true,
      "emailDomainCatchallVerdict": "ava@example.com",
      "emailerCampaignIds": [
        "ava@example.com"
      ],
      "emailFromCustomer": true,
      "emailNeedsTickling": true,
      "emailSource": "ava@example.com",
      "emailStatus": "ava@example.com",
      "emailStatusUnavailableReason": "ava@example.com",
      "emailTrueStatus": "ava@example.com",
      "emailUnsubscribed": true,
      "existenceLevel": "string",
      "extrapolatedEmailConfidence": 1,
      "facebookUrl": "https://example.com",
      "firstName": "Ava",
      "formattedAddress": "string",
      "freeDomain": true,
      "godmodeApolloCreator": true,
      "hasEmailArcgateRequest": true,
      "hasPendingEmailArcgateRequest": true,
      "headline": "string",
      "hubspotCompanyId": "string",
      "hubspotRecordUrl": "https://example.com",
      "hubspotVid": "string",
      "id": "string",
      "intentStrength": 1,
      "labelIds": [
        "string"
      ],
      "lastActivityDate": "2026-05-07T12:00:00.000Z",
      "lastName": "Chen",
      "linkedinUid": "https://example.com",
      "linkedinUrl": "https://example.com",
      "mergedCrmIds": [
        "string"
      ],
      "name": "Ava Chen",
      "organization": {},
      "organizationId": "string",
      "organizationName": "Ava Chen",
      "originalSource": "string",
      "outboundSubscriptions": [
        {}
      ],
      "ownerId": "string",
      "personDeleted": true,
      "personId": "string",
      "phoneNumbers": [
        {}
      ],
      "photoUrl": "https://example.com",
      "postalCode": "string",
      "presentRawAddress": "string",
      "queuedForCrmPush": true,
      "salesforceAccountId": "string",
      "salesforceContactId": "string",
      "salesforceId": "string",
      "salesforceLeadId": "string",
      "sanitizedPhone": "string",
      "showIntent": true,
      "source": "string",
      "sourceDisplayName": "Ava Chen",
      "state": "string",
      "streetAddress": "string",
      "suggestedFromRuleEngineConfigId": "string",
      "timeZone": "string",
      "title": "string",
      "twitterUrl": "https://example.com",
      "typedCustomFields": {},
      "updatedAt": "2026-05-07T12:00:00.000Z",
      "updatedEmailTrueStatus": "ava@example.com"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `account` | object |  |
| `accountId` | string |  |
| `accountPhoneNote` | string |  |
| `callOptedOut` | boolean |  |
| `city` | string |  |
| `contactCampaignStatuses` | array<object> |  |
| `contactEmails` | array<object> |  |
| `contactJobChangeEvent` | object |  |
| `contactRoles` | array<object> |  |
| `contactStageId` | string |  |
| `country` | string |  |
| `createdAt` | date |  |
| `creatorId` | string |  |
| `crmId` | string |  |
| `crmOwnerId` | string |  |
| `crmRecordUrl` | string |  |
| `customFieldErrors` | object |  |
| `directDialEnrichmentFailedAt` | date |  |
| `directDialStatus` | string |  |
| `directoryUrl` | string |  |
| `email` | string |  |
| `emailDomainCatchall` | boolean |  |
| `emailDomainCatchallVerdict` | string |  |
| `emailerCampaignIds` | array<string> |  |
| `emailFromCustomer` | boolean |  |
| `emailNeedsTickling` | boolean |  |
| `emailSource` | string |  |
| `emailStatus` | string |  |
| `emailStatusUnavailableReason` | string |  |
| `emailTrueStatus` | string |  |
| `emailUnsubscribed` | boolean |  |
| `existenceLevel` | string |  |
| `extrapolatedEmailConfidence` | number |  |
| `facebookUrl` | string |  |
| `firstName` | string |  |
| `formattedAddress` | string |  |
| `freeDomain` | boolean |  |
| `godmodeApolloCreator` | boolean |  |
| `hasEmailArcgateRequest` | boolean |  |
| `hasPendingEmailArcgateRequest` | boolean |  |
| `headline` | string |  |
| `hubspotCompanyId` | string |  |
| `hubspotRecordUrl` | string |  |
| `hubspotVid` | string |  |
| `id` | string |  |
| `intentStrength` | number |  |
| `labelIds` | array<string> |  |
| `lastActivityDate` | date |  |
| `lastName` | string |  |
| `linkedinUid` | string |  |
| `linkedinUrl` | string |  |
| `mergedCrmIds` | array<string> |  |
| `name` | string |  |
| `organization` | object |  |
| `organizationId` | string |  |
| `organizationName` | string |  |
| `originalSource` | string |  |
| `outboundSubscriptions` | array<object> |  |
| `ownerId` | string |  |
| `personDeleted` | boolean |  |
| `personId` | string |  |
| `phoneNumbers` | array<object> |  |
| `photoUrl` | string |  |
| `postalCode` | string |  |
| `presentRawAddress` | string |  |
| `queuedForCrmPush` | boolean |  |
| `salesforceAccountId` | string |  |
| `salesforceContactId` | string |  |
| `salesforceId` | string |  |
| `salesforceLeadId` | string |  |
| `sanitizedPhone` | string |  |
| `showIntent` | boolean |  |
| `source` | string |  |
| `sourceDisplayName` | string |  |
| `state` | string |  |
| `streetAddress` | string |  |
| `suggestedFromRuleEngineConfigId` | string |  |
| `timeZone` | string |  |
| `title` | string |  |
| `twitterUrl` | string |  |
| `typedCustomFields` | object |  |
| `updatedAt` | date |  |
| `updatedEmailTrueStatus` | string |  |

## Native endpoint

Through the native Apollo API, this operation is `POST v1/contacts/search` (base URL `https://app.apollo.io/api`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/search-for-contacts.md) for the provider-specific parameters and requirements.

