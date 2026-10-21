# Zenoti: Get Sales Accrual Report



```
GET https://connect.mindcloud.co/v1/universal/zenoti/latest/actions/get-sales-accrual-report
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Zenoti `connectionId` ([setup](../authentication.md)).

This action also supports [pagination](../pagination.md) (`limit`, `offset`).

## Example request

```bash
curl -X GET "https://connect.mindcloud.co/v1/universal/zenoti/latest/actions/get-sales-accrual-report?connectionId=$CONNECTION_ID&limit=25&offset=0&startDate=2026-05-07T12%3A00%3A00.000Z&endDate=2026-05-07T12%3A00%3A00.000Z" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY"
```

```js
const params = new URLSearchParams({
  connectionId,
  limit: '25',
  offset: '0',
  "startDate": "2026-05-07T12:00:00.000Z",
  "endDate": "2026-05-07T12:00:00.000Z"
});

const response = await fetch(`https://connect.mindcloud.co/v1/universal/zenoti/latest/actions/get-sales-accrual-report?${params}`, {
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
| `center_ids[].center` | list | no |  |
| `invoiceStatuses[].invoiceStatus` | list | no | One of: `0`, `4`. |
| `itemTypes[].itemType` | list | no | One of: `DayPromoPackage`, `GiftCard`, `Membership`, `OtherFees`, `Package`, `PrepaidCard`, `Product`, `Service`. |
| `paymentTypes[].paymentType` | list | no | One of: `0`, `1`, `10`, `16`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`. |
| `saleTypes[].saleType` | list | no | One of: `0`, `1`, `2`, `3`. |
| `startDate` | date | yes |  |
| `endDate` | date | yes |  |
| `center_ids[]` | array | no |  |
| `itemTypes[]` | array | no |  |
| `paymentTypes[]` | array | no |  |
| `saleTypes[]` | array | no |  |
| `invoiceStatuses[]` | array | no |  |
| `includeTotal` | boolean | no | Default: `false`. |

## Response

```json
{
  "success": true,
  "data": [
    {
      "additionalInvoiceField": "string",
      "brandId": "string",
      "brandName": "Ava Chen",
      "bundleName": "Ava Chen",
      "businessUnit": "string",
      "businessUnitId": "string",
      "centerCode": "string",
      "centerId": "string",
      "centerName": "Ava Chen",
      "collected": 1,
      "companyName": "Ava Chen",
      "createdBy": "string",
      "createdById": "string",
      "discount": 1,
      "due": 1,
      "guestCode": "string",
      "guestGender": 1,
      "guestId": "string",
      "guestName": "Ava Chen",
      "guestNationality": "string",
      "invoiceClosedDate": "2026-05-07T12:00:00.000Z",
      "invoiceDate": "2026-05-07T12:00:00.000Z",
      "invoiceId": "string",
      "invoiceItemId": "string",
      "invoiceNo": "string",
      "invoiceSource": "string",
      "itemCategory": "string",
      "itemCategoryCode": "string",
      "itemCode": "string",
      "itemId": "string",
      "itemName": "Ava Chen",
      "itemSubCategory": "string",
      "itemType": "string",
      "nonTaxableRedemption": 1,
      "paymentType": "string",
      "price": 1,
      "qty": 1,
      "receiptNo": "string",
      "redeemed": 1,
      "referralSource": "string",
      "saleDate": "2026-05-07T12:00:00.000Z",
      "salesExcludingRedemption": 1,
      "salesExcTax": 1,
      "salesIncTax": 1,
      "saleType": "string",
      "serviceShopCost": 1,
      "soldBy": "string",
      "soldByCode": "string",
      "soldById": "string",
      "status": "string",
      "tax": 1,
      "taxableRedemption": 1,
      "taxRedeemedByGiftCard": 1,
      "taxRedeemedByLoyaltyPoints": 1,
      "totalGroupCount": 1,
      "vendorId": "string",
      "vendorName": "Ava Chen"
    }
  ],
  "meta": {}
}
```

### Response fields

| Key | Type | Description |
| --- | --- | --- |
| `additionalInvoiceField` | string |  |
| `brandId` | string |  |
| `brandName` | string |  |
| `bundleName` | string |  |
| `businessUnit` | string |  |
| `businessUnitId` | string |  |
| `centerCode` | string |  |
| `centerId` | string |  |
| `centerName` | string |  |
| `collected` | number |  |
| `companyName` | string |  |
| `createdBy` | string |  |
| `createdById` | string |  |
| `discount` | number |  |
| `due` | number |  |
| `guestCode` | string |  |
| `guestGender` | number |  |
| `guestId` | string |  |
| `guestName` | string |  |
| `guestNationality` | string |  |
| `invoiceClosedDate` | date |  |
| `invoiceDate` | date |  |
| `invoiceId` | string |  |
| `invoiceItemId` | string |  |
| `invoiceNo` | string |  |
| `invoiceSource` | string |  |
| `itemCategory` | string |  |
| `itemCategoryCode` | string |  |
| `itemCode` | string |  |
| `itemId` | string |  |
| `itemName` | string |  |
| `itemSubCategory` | string |  |
| `itemType` | string |  |
| `nonTaxableRedemption` | number |  |
| `paymentType` | string |  |
| `price` | number |  |
| `qty` | number |  |
| `receiptNo` | string |  |
| `redeemed` | number |  |
| `referralSource` | string |  |
| `saleDate` | date |  |
| `salesExcludingRedemption` | number |  |
| `salesExcTax` | number |  |
| `salesIncTax` | number |  |
| `saleType` | string |  |
| `serviceShopCost` | number |  |
| `soldBy` | string |  |
| `soldByCode` | string |  |
| `soldById` | string |  |
| `status` | string |  |
| `tax` | number |  |
| `taxableRedemption` | number |  |
| `taxRedeemedByGiftCard` | number |  |
| `taxRedeemedByLoyaltyPoints` | number |  |
| `totalGroupCount` | number |  |
| `vendorId` | string |  |
| `vendorName` | string |  |

## Native endpoint

Through the native Zenoti API, this operation is `POST reports/sales/accrual_basis/flat_file` (base URL `https://api.zenoti.com/v1/`). The Universal API call above is translated to it by MindCloud, including authentication and pagination. See the [native action reference](../../native-api/actions/get-sales-accrual-report.md) for the provider-specific parameters and requirements.

