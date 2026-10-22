# Update Customer Action with Viewpoint Vista

## Endpoint

- **Method:** `POST`
- **Path:** `v1/direct/subscribers/:subscriber_code/vista/:api/2/data/customers/actions/change`
- **Base URL:** `https://api.xchange.trimble.com/connect/`
- **API:** REST
- **Official documentation:** [Update Customer Action](https://direct-api.xchange.trimble.com/reference/post-directsubscriberssubscriber_codevistaar2datacustomersactionsadd)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `ARCo` | body | `number` | no | — |
| `CompanyContact.Phone` | body | `string` | no | — |
| `CompanyContact.Fax` | body | `string` | no | — |
| `Name` | body | `string` | no | — |
| `CompanyContact.Contact` | body | `string` | no | — |
| `RecType` | body | `number` | no | Receivable Type key for the AR company. Optional; Vista uses the company default when omitted. |
| `CompanyContact.contactExt` | body | `string` | no | — |
| `MailingAddress` | body | `object` | no | — |
| `BillingAddress` | body | `object` | no | — |
| `CompanyContact.EMail` | body | `string` | no | — |
| `CompanyContact.URL` | body | `string` | no | — |
| `PayTerms` | body | `string` | no | — |
| `TaxCode` | body | `string` | no | — |
| `CompanyContact` | body | `object` | no | — |
| `__key` | body | `object` | no | — |
| `__custom_fields` | body | `object` | no | — |
