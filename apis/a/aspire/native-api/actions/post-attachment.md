# Post Attachment with Aspire

## Endpoint

- **Method:** `POST`
- **Path:** `/Attachments`
- **Base URL:** `https://{environment}.youraspire.com/`
- **Official documentation:** [Post Attachment](https://guide.youraspire.com/apidocs/attachments-2)

## Headers

Send these additional headers for this operation:

| Header | Value |
| --- | --- |
| `Accept` | `application/json;odata.metadata=minimal;odata.streaming=true, application/json;odata.metadata=minimal;odata.streaming=false, application/json;odata.metadata=minimal, application/json;odata.metadata=full;odata.streaming=true, application/json;odata.metadata=full;odata.streaming=false, application/json;odata.metadata=full, application/json;odata.metadata=none;odata.streaming=true, application/json;odata.metadata=none;odata.streaming=false, application/json;odata.metadata=none, application/json;odata.streaming=true, application/json;odata.streaming=false, application/json, application/xml, application/prs.odatatestxx-odata, text/plain, text/json` |

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `AttachmentTypeId` | body | `list<number>` | yes | — |
| `FileName` | body | `string` | yes | — |
| `FileData` | body | `file` | yes | File content as a base64-encoded string. When the user attached a file in the chat, pass the attachment reference provided by the chat. |
| `ObjectCode` | body | `list<string>` | yes | Type of record receiving the attachment. Common values: WorkTicket (set objectId to workTicketID, not the ticket number), Opportunity (set objectId to opportunityID), and Receipt (set objectId to receiptID). Use listObjectCodes for the full list of supported values; do not guess the record type. |
| `ObjectId` | body | `number` | yes | — |
| `AttachToInvoice` | body | `boolean` | no | Only valid for Opportunity attachments. For any other objectCode, omit this field entirely; Aspire rejects it even when false. |
| `ExposeToCrew` | body | `boolean` | no | — |
