# Sage Intacct: Native API Reference

A consolidated summary of Sage Intacct's API configuration and 25 documented operations, with links to official documentation.

- **Official docs:** https://developer.intacct.com/api/
- **REST base URL:** `https://api.intacct.com/ia/xml/xmlgw.phtml`
- **Read By Query base URL:** `https://api.intacct.com/ia/xml/xmlgw.phtml`

## Authentication

### Custom

### Credentials

- **Company Id:** `companyId` · required
- **User Id:** `userId` · required
- **User Password:** `userPassword` · required
- **Sender Password:** `senderPassword` · required
- **Sender Id:** `senderId` · required

[Official authentication documentation](https://developer.intacct.com/web-services/#authentication)

## API conventions

### REST

Request bodies use XML.

Shared headers:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/xml` |

Shared parameters:

| Parameter | Location | Type | Required |
| --- | --- | --- | --- |
| `SenderId` | body | `string` | no |

Responses from this API use XML.

### Read By Query

Request bodies use XML.

Shared headers:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/xml` |

Responses from this API use XML.

## Pagination

- **REST:** Use `pagesize` in the request body to set the page size (default 100; accepted range 1–1000). Use `offset` in the request body as the record offset.
- **Read By Query:** Use `pagesize` in the request body to set the page size (default 100; accepted range 1–1000). Use `cursor` in the request body as the pagination cursor.

## Endpoints (25 documented)

| Operation | API | Method & path | Vendor docs |
| --- | --- | --- | --- |
| [Check GLBATCH Duplicate](actions/check-glbatch-duplicate.md) | REST | `POST` |  |
| [Create Attachment](actions/create-attachment.md) | REST | `POST` | [docs](https://developer.intacct.com/api/company-console/attachments/#create-attachment-legacy) |
| [Create Budget](actions/create-budget.md) | REST | `POST /` | [docs](https://developer.intacct.com/api/general-ledger/budgets/) |
| [Create Invoice](actions/create-invoice.md) | REST | `POST` | [docs](https://developer.intacct.com/api/accounts-receivable/invoices/#create-invoice-legacy) |
| [Create Item](actions/create-item.md) | REST | `POST` |  |
| [Create Item New](actions/create-item-2.md) | REST | `POST` |  |
| [Create Order Entry Document](actions/create-order-entry-document.md) | REST | `POST https://api.intacct.com/ia/api/v1/objects/order-entry/document:::documentName` | [docs](https://developer.sage.com/intacct/apis/intacct/1/intacct-openapi/groups/order-entry/groups/documents/tags/order_entry_documents/paths/create-order-entry-named-document) |
| [Create Sales Invoice](actions/create-sales-invoice.md) | REST | `POST` | [docs](https://developer.intacct.com/api/accounts-receivable/invoices/#create-invoice-legacy) |
| [Create So Transaction](actions/create-so-transaction.md) | REST | `POST https://api.intacct.com/ia/xml/xmlgw.phtml` | [docs](https://developer.intacct.com/api/order-entry/order-entry-transactions/#create-order-entry-transaction-legacy) |
| [Create Bill Item](actions/createbillitem.md) | REST | `POST` |  |
| [Create Journal](actions/createjournal.md) | REST | `POST` | [docs](https://developer.intacct.com/api/accounts-receivable/invoices/#create-invoice-legacy) |
| [Get Custom Object](actions/get-custom-object.md) | REST | `POST` |  |
| [Get Fields for Object](actions/get-fields.md) | REST | `POST` |  |
| [Get Full Item](actions/get-full-item.md) | REST | `POST` |  |
| [Get Full Item By Name](actions/get-full-item-by-name.md) | REST | `POST` |  |
| [List Contacts](actions/list-contacts.md) | REST | `POST /` | [docs](https://developer.intacct.com/api/project-resource-mgmt/projects/#query-and-list-projects) |
| [List Projects](actions/list-projects.md) | REST | `POST /` | [docs](https://developer.intacct.com/api/project-resource-mgmt/projects/#query-and-list-projects) |
| [Post Raw to Stripe](actions/post-raw-to-stripe.md) | REST | `POST` |  |
| [Query Object](actions/query-object.md) | REST | `POST /` | [docs](https://developer.intacct.com/web-services/queries/) |
| [Query Object Sum](actions/query-object-sum.md) | REST | `POST` |  |
| [Read Bank Deposits](actions/read-bank-deposits.md) | REST | `POST` |  |
| [Read By Query](actions/read-by-query.md) | Read By Query | `POST` |  |
| [Update Invoice](actions/update-invoice.md) | REST | `POST` |  |
| [Update Item](actions/update-item.md) | REST | `POST` |  |
| [Update Journal](actions/update-journal.md) | REST | `POST` | [docs](https://developer.intacct.com/api/accounts-receivable/invoices/#create-invoice-legacy) |
