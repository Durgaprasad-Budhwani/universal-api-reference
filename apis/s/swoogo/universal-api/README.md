# <img src="https://images.mindcloud.co/apps/icons/swoogo_1791589994893.png" alt="Swoogo logo" width="28" height="28"> Swoogo: Universal API

Manage events, registrants, sessions, and attendance

- **Interactive docs:** https://mindcloud.co/docs/universal/rest/swoogo/latest
- **Category:** Marketing / Events & Webinars
- **Actions:** 3
- **OpenAPI specification:** [openapi.json](openapi.json)
- **Vendor website:** https://swoogo.events/
- **Vendor API docs:** https://swoogo.readme.io/reference

## Quickstart

Every action below is called through one REST interface, authenticated with a MindCloud API key and a `connectionId`.

Read more in [authentication.md](authentication.md).

For example, to [Get Registrant](actions/get-registrant.md):

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/swoogo/latest/actions/get-registrant?connectionId=$CONNECTION_ID&registrantId=1" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

## Actions (3)

### Event

| Action | Method | Description |
| --- | --- | --- |
| [List Events](actions/list-events.md) | GET |  |

### Registrant

| Action | Method | Description |
| --- | --- | --- |
| [Get Registrant](actions/get-registrant.md) | GET |  |
| [List Registrants](actions/list-registrants.md) | GET |  |

