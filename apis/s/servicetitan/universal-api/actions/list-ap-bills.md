# ServiceTitan: List AP Bills

Lists AP bills with line items and accounting details. Filter by bill type, sync status, and creation or modification dates.

```
GET https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-ap-bills
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a ServiceTitan `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-ap-bills?connectionId=$CONNECTION_ID&limit=25&offset=0" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0'
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/servicetitan/latest/actions/list-ap-bills?${params}`, {
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
| `ids` | string | no | Comma-separated list of specific AP bill IDs to retrieve Accepts multiple values in one string, delimited by `,`. |
| `batchId` | number | no | Filter by specific batch ID |
| `batchNumber` | number | no | Filter by batch number |
| `billNumber` | string | no | Filter by bill number (partial match supported) |
| `businessUnitIds` | string | no | Comma-separated list of business unit IDs to filter by Accepts multiple values in one string, delimited by `,`. |
| `customField` | object | no |  |
| `customField.fields` | object | no | Dictionary of name-value pairs |
| `customField.operator` | list<string> | no | Operator to be used between the name-value pairs. Can be "Or" or "And", default is "And". Values: [And, Or] One of: `And`, `Or`. |
| `dateFrom` | date | no | Filter bills created on or after this date |
| `dateTo` | date | no | Filter bills created on or before this date |
| `jobNumber` | string | no | Filter by job number (partial match supported) |
| `purchaseOrderNumber` | string | no | Filter by purchase order number (partial match supported) |
| `purchaseOrderTypes` | string | no | Comma-separated list of purchase order types to filter by Accepts multiple values in one string, delimited by `,`. |
| `syncStatuses` | list<string> | no | Filter by sync status values One of: `Exported`, `Pending`, `Posted`, `PostedAndExported`. Accepts multiple values as an array. |
| `statuses` | list<string> | no | Filter by bill status values One of: `Canceled`, `Discrepancy`, `Reconciled`, `Unreconciled`. Accepts multiple values as an array. |
| `sources` | list<string> | no | Filter by bill source values One of: `API`, `OCR`, `Purchasing`, `Recurring`, `Standalone`, `Undefined`. Accepts multiple values as an array. |
| `minCost` | number | no | Filter bills with cost greater than or equal to this amount |
| `maxCost` | number | no | Filter bills with cost less than or equal to this amount |
| `billType` | list<string> | no | Filter by bill type (defaults to Procurement). Values: [NotSet, Procurement, ApBill] One of: `ApBill`, `NotSet`, `Procurement`. |
| `createdBefore` | date | no | Return items created before certain date/time (in UTC) |
| `createdOnOrAfter` | date | no | Return items created on or after certain date/time (in UTC) |
| `modifiedBefore` | date | no | Return items modified before certain date/time (in UTC) |
| `modifiedOnOrAfter` | date | no | Return items modified on or after certain date/time (in UTC) |
| `dateReconciledBefore` | date | no | Filter by bills reconciled on or before this date |
| `dateReconciledOnOrAfter` | date | no | Filter by bills reconciled after this date |
| `threeWayMatchDiscrepancy` | list<string> | no | Filter by three-way match discrepancy status. Values: [NoDiscrepancy, Discrepancy] One of: `Discrepancy`, `NoDiscrepancy`. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `includeTotal` | boolean | no |  |

## Response

```json
{
  "success": true,
  "data": [
    {
      "batch": {},
      "billAmount": "string",
      "billDate": "string",
      "billType": "string",
      "budgetCodeId": 1,
      "businessUnit": {},
      "canceledBy": "string",
      "createdBy": "string",
      "createdOn": "string",
      "customFields": {},
      "dateCanceled": "string",
      "dateReconciled": "string",
      "doNotPay": true,
      "dueDate": "string",
      "earlyDiscountDate": "string",
      "expenseItems": [
        {}
      ],
      "id": 1,
      "items": [
        {}
      ],
      "jobId": 1,
      "jobNumber": "string",
      "landedCostMethod": 1,
      "modifiedOn": "string",
      "otherAmount": "string",
      "postDate": "string",
      "postTaxCharge": "string",
      "postTaxDiscountAmount": "string",
      "preTaxCharge": "string",
      "preTaxDiscountAmount": "string",
      "purchaseOrderId": 1,
      "referenceNumber": "string",
      "remittanceVendorInfo": {},
      "shippingAmount": "string",
      "shipTo": {},
      "shipToDescription": "string",
      "source": "string",
      "status": "string",
      "summary": "string",
      "syncStatus": "string",
      "taxAmount": "string",
      "taxZone": {},
      "termName": "Ava Chen",
      "vendor": {},
      "vendorInvoiceTotal": "string",
      "vendorNumber": "string"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `batch` | object | Batch the bill belongs to. |
| `billAmount` | string | Total bill amount. |
| `billDate` | string | Invoice date of the bill. |
| `billType` | string | Type of the bill. |
| `budgetCodeId` | number | Budget code ID. |
| `businessUnit` | object | Business unit the bill belongs to. |
| `canceledBy` | string | User who canceled the bill. |
| `createdBy` | string | User who created the bill. |
| `createdOn` | string | Timestamp when the bill was created. |
| `customFields` | object | Custom fields on the bill. |
| `dateCanceled` | string | Date the bill was canceled. |
| `dateReconciled` | string | Date the bill was reconciled. |
| `doNotPay` | boolean | Whether the bill is excluded from payment. |
| `dueDate` | string | Payment due date. |
| `earlyDiscountDate` | string | Early payment discount date. |
| `expenseItems` | array<object> | Expense items on the bill. |
| `id` | number | AP bill ID. |
| `items` | array<object> | Line items on the bill. |
| `jobId` | number | Related job ID. |
| `jobNumber` | string | Related job number. |
| `landedCostMethod` | number | Landed cost method. |
| `modifiedOn` | string | Timestamp when the bill was last modified. |
| `otherAmount` | string | Other amount. |
| `postDate` | string | Date the bill was posted. |
| `postTaxCharge` | string | Post-tax charge. |
| `postTaxDiscountAmount` | string | Post-tax discount amount. |
| `preTaxCharge` | string | Pre-tax charge. |
| `preTaxDiscountAmount` | string | Pre-tax discount amount. |
| `purchaseOrderId` | number | Related purchase order ID. |
| `referenceNumber` | string | Reference number of the bill. |
| `remittanceVendorInfo` | object | Remittance vendor information. |
| `shippingAmount` | string | Shipping amount. |
| `shipTo` | object | Ship-to address. |
| `shipToDescription` | string | Ship-to description. |
| `source` | string | Source of the bill. |
| `status` | string | Reconciliation status of the bill. |
| `summary` | string | Bill summary. |
| `syncStatus` | string | Sync status of the bill. |
| `taxAmount` | string | Tax amount. |
| `taxZone` | object | Tax zone for the bill. |
| `termName` | string | Payment term name. |
| `vendor` | object | Vendor for the bill. |
| `vendorInvoiceTotal` | string | Vendor invoice total. |
| `vendorNumber` | string | Vendor number. |

## Native endpoint

Through the native ServiceTitan API, this operation is `GET accounting/v2/tenant/{{credentials.tenant}}/ap-bills` (base URL `https://{{credentials.baseUrl}}/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/list-ap-bills.md) for the provider-specific parameters and requirements.

