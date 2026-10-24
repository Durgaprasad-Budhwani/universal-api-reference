# <img src="https://images.mindcloud.co/apps/icons/epicor-prophet21_1791908894393.png" alt="Epicor Prophet 21 logo" width="28" height="28"> Epicor Prophet 21: Universal API

Connect to Epicor Prophet 21 to read customers, contacts, addresses, sales orders, quotes, order lines, and product groups.

- **Interactive docs:** https://mindcloud.co/docs/universal/rest/epicorProphet21/latest
- **Category:** Commerce / ERP
- **Actions:** 11
- **OpenAPI specification:** [openapi.json](openapi.json)
- **Vendor website:** https://www.epicor.com/en-us/industry-productivity-solutions/distribution/prophet-21/

## Quickstart

Every action below is called through one REST interface, authenticated with a MindCloud API key and a `connectionId`.

Read more in [authentication.md](authentication.md).

For example, to [List Product Groups](actions/list-product-groups.md):

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/epicorProphet21/latest/actions/list-product-groups?connectionId=$CONNECTION_ID" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

## Actions (11)

### Addresses

| Action | Method | Description |
| --- | --- | --- |
| [List Addresses](actions/list-addresses.md) | GET |  |
| [List Entity Addresses](actions/list-entity-addresses.md) | GET |  |

### Contacts

| Action | Method | Description |
| --- | --- | --- |
| [List Contacts](actions/list-contacts.md) | GET |  |
| [List Entity Contacts](actions/list-entity-contacts.md) | GET |  |

### Customers

| Action | Method | Description |
| --- | --- | --- |
| [List Customers](actions/list-customers.md) | GET |  |
| [List Entity Customers](actions/list-entity-customers.md) | GET |  |

### Order Lines

| Action | Method | Description |
| --- | --- | --- |
| [List Order Lines](actions/list-order-lines.md) | GET |  |

### Orders

| Action | Method | Description |
| --- | --- | --- |
| [List Sales Orders](actions/list-sales-orders.md) | GET |  |

### Other

| Action | Method | Description |
| --- | --- | --- |
| [List Product Groups](actions/list-product-groups.md) | GET |  |
| [Query Data View](actions/query-data-view.md) | GET |  |

### Quotes

| Action | Method | Description |
| --- | --- | --- |
| [List Quotes](actions/list-quotes.md) | GET |  |

