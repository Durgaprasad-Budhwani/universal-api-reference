# Viewpoint Vista: Add Change Order Batch Entry



```
POST https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/add-change-order-batch-entry
```

Authenticate with `Authorization: Bearer $MINDCLOUD_API_KEY` and pass a Viewpoint Vista `connectionId` ([setup](../authentication.md)).

## Example request

```bash
curl -X POST "https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/add-change-order-batch-entry" \
  -H "Authorization: Bearer $MINDCLOUD_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "connectionId": "$CONNECTION_ID",
  "co": 1,
  "mth": "string",
  "batchId": 1,
  "po": "string",
  "poItem": 1
}'
```

```js
const response = await fetch('https://connect.mindcloud.co/v1/universal/viewpointVista/latest/actions/add-change-order-batch-entry', {
  method: 'POST',
  headers: {
    Authorization: `Bearer ${process.env.MINDCLOUD_API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    connectionId,
    "co": 1,
    "mth": "string",
    "batchId": 1,
    "po": "string",
    "poItem": 1
  })
});

const { success, data } = await response.json();
```

## Inputs

Arguments are sent as JSON body fields ([conventions](../arguments.md)).

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `co` | number | yes | Company. Key to the change order batch. |
| `mth` | string | yes | Batch posting month in YYYY-MM-01 format. |
| `batchId` | number | yes | Change order batch ID. |
| `po` | string | yes | Purchase order number. |
| `poItem` | number | yes | Purchase order line item number. |
| `newLineItem` | object | no | Optional details used when adding a new PO line item. |
| `newLineItem.itemType` | list<number> | no | Required only when adding a new purchase order line. 1: Job; 2: Inventory; 3: Expense; 4: Equipment; 5: EM Work Order; 6: SM Work Order. Leave all New Line Item fields empty for an existing line. One of: `1`, `2`, `3`, `4`, `5`, `6`. |
| `newLineItem.jcCo` | number | no | Required when adding a new line with item type 1. Used for item type 1. Key to jc/jobs(JCCo, Job). |
| `newLineItem.job` | string | no | Required when adding a new line with item type 1. Used for item type 1. Key to jc/jobs(JCCo, Job). |
| `newLineItem.material` | string | no | Material code. Required for Inventory (Item Type 2); optional for other types. Material group is resolved from the applicable company. |
| `newLineItem.inCo` | number | no | Required when adding a new line with item type 2. Used for item type 2. Key to in/locations(INCo, Loc). |
| `newLineItem.loc` | string | no | Required when adding a new line with item type 2. Used for item type 2. Key to in/locations(INCo, Loc). |
| `newLineItem.glCo` | number | no | Required when adding a new line with item type 3. Used for item type 3. Key to gl/chart_of_accounts(GLCo, GLAcct). |
| `newLineItem.emCo` | number | no | Equipment company. Required for Equipment (4) and EM Work Order (5). |
| `newLineItem.equip` | string | no | Required when adding a new line with item type 4. Used for item type 4. Key to em/equipment(EMCo, Equipment). |
| `newLineItem.costCode` | string | no | Equipment cost code. Required for Equipment (4); for EM Work Order (5), may be ignored when specified by the work order item. |
| `newLineItem.emcType` | number | no | Required when adding a new line with item type 4, 5. Used for item type 4, 5. key to CostTypes array in em/cost_codes(EMGroup, CostCode, $.CostTypes.CostType). |
| `newLineItem.wo` | string | no | Required when adding a new line with item type 5. Used for item type 5. Equipment Work Order. |
| `newLineItem.woItem` | number | no | Required when adding a new line with item type 5. Used for item type 5. Equipment Work Order Item. |
| `newLineItem.smCo` | number | no | Required when adding a new line with item type 6. Used for item type 6. SM Company. |
| `newLineItem.smWorkOrder` | number | no | Required when adding a new line with item type 6. Used for item type 6. SM Work Order |
| `newLineItem.smScope` | number | no | Required when adding a new line with item type 6. Used for item type 6. SM Scope |
| `newLineItem.smCostType` | number | no | Required when adding a new line with item type 6. Used for item type 6. SM Cost Type. |

### Advanced

| Key | Type | Required | Description |
| --- | --- | --- | --- |
| `pocoNum` | number | no | Optional PO change order number; the next available number is used when omitted. |
| `changeOrder` | string | no | Optional change order number used to group related changes. |
| `actDate` | string | no | Optional action date in YYYY-MM-DD format. |
| `description` | string | no | Optional change description. |
| `changeCurUnits` | string | no | Optional change to current units for non-LS items. |
| `changeBOUnits` | string | no | Optional change to backorder units for non-LS items. |
| `changeCurCost` | string | no | Optional change to current cost for LS items. |
| `changeBOCost` | string | no | Optional change to backorder cost for LS items. |
| `newLineItem.description` | string | no | Optional. if omitted, null will be defaulted. |
| `newLineItem.phase` | string | no | Used for item type 1. Key to jc/job_phases(JCCo, Job, PhaseGroup, Phase) The PhaseGroup will be selected based on the JCCo value. Optional. If omitted, it will be defaulted based on Vista defaulting logic. If a default cannot be applied, this action may fail or force a Vista user to supply this value before posting. |
| `newLineItem.jccType` | number | no | Used for item type 1. Key to CostTypes array in jc/job_phases(JCCo, Job, PhaseGroup, Phase, $.CostTypes.CostType) Optional. If omitted, it will be defaulted based on Vista defaulting logic. If a default cannot be applied, this action may fail or force a Vista user to supply this value before posting. |
| `newLineItem.glAcct` | string | no | GL account. Optional; company selection and defaults depend on Item Type and Vista configuration. Some item types disallow account overrides. |
| `newLineItem.vendMatId` | string | no | Key to po/vendor_materials(VendorGroup, Vendor, MaterlGroup, Material, UM). Vendor's Material Number. Optional. If Omitted, it will be defaulted based Vista defaulting behavior. |
| `newLineItem.recvYn` | list<string> | no | Receiving in PO Module. Optional. If omitted, N will be defaulted. Send Y if this item will be received in the PO module. One of: `N`, `Y`. |
| `newLineItem.reqDate` | date | no | Required Date. Format: YYYY-MM-DD. Optional. If not provided it will be defaulted to $.ExpDate. |
| `newLineItem.payCategory` | number | no | Key to ap/pay_categories(APCo, PayCategory). APCo will be defaulted based on Vista defaulting logic. Optional. If omitted, it will be defaulted based on Vista defaulting behavior. In some configurations, overrides are not allowed. Providing this property when overrides are not allowed will result in an error. |
| `newLineItem.payType` | number | no | Key to ap/pay_categories(APCo, PayCategory). APCo will be defaulted based on Vista defaulting logic. Optional. If omitted Vista defaulted based on Vista defaulting behavior. In some configurations, overrides are not allowed. Providing this property when overrides are not allowed will result in an error. In all cases if PayCategory is provided or defaulted this value must be in the PayCategory or in no PayCategory |
| `newLineItem.amount` | object | no | If omitted, each property will be defaulted as noted on each property. |
| `newLineItem.amount.um` | string | no | Key to hq/units_of_measures(UM). Optional. If omitted, it will be defaulted based on Vista defaulting behavior. |
| `newLineItem.amount.origUnitCost` | string | no | Optional. If omitted, it will be defaulted based on Vista defaulting logic. If UM is LS, this value is ignored and will be set to 0. |
| `newLineItem.amount.origEcm` | list<string> | no | Options: E-CostPerEach, C-CostPer100, M-CostPer1000. Optional. If omitted, it will be defaulted based on Vista defaulting behavior. If UM is LS, this value is ignored and will be set to null. One of: `C`, `E`, `M`, `null`. |
| `newLineItem.tax` | object | no | Optional. If omitted each property will be be defaulted based on Vista defaulting behavior. |
| `newLineItem.tax.taxType` | list<number> | no | Options: 1-Sales, 2-Use, 3-VAT. Optional. If not provided, it will be defaulted based on Vista defaulting behavior. One of: `1`, `2`, `3`. |
| `newLineItem.tax.taxCode` | string | no | Key to hq/tax_codes(TaxGroup, TaxCode). TaxGroup will be determined based on JCCo. Optional. If not provided, it will be defaulted based on Vista defaulting behavior. |
| `newLineItem.supplier` | number | no | Key to ap/vendors(SupplierGroup, Supplier) for supplier for this line. SupplierGroup is defaulted based on Co. Optional. If omitted, null will be defaulted. |
| `newLineItem.notes` | string | no | Optional. If not provided, null will be defaulted. |
| `newLineItem.__custom_fields` | object | no | Add a property to this object for each user defined field to be set. Property name set to the user defined field name. |
| `newLineItem.compType` | string | no | Used for item type 4. Optional. If omitted, null will be defaulted. |
| `newLineItem.component` | string | no | Used for item type 4. Optional. If omitted, null will be defaulted. |
| `newLineItem.smPhase` | string | no | Used for item type 6. Key to jc/job_phases(SMPhaseGroup, SMPhase). SMPhaseGroup will be defaulted based on the JCCo associated to the SM Work Order. Optional. This value should only be supplied if the SM Scope does not have a Phase assigned. |
| `newLineItem.smjcCostType` | number | no | Used for item type 6. Key to CostTypes array in jc/job_phases(JCCo, Job, PhaseGroup, Phase, $.CostTypes.CostType) Optional. This value should only be supplied if the SM Scope does not have a CostType assigned. |
| `notes` | string | no | Optional entry notes. |
| `__custom_fields` | object | no | Optional Vista user-defined fields, keyed by field name. |

## Response

The response envelope is `{ "success": true, "data": [...], "meta": {} }`. The `data` schema for this action is dynamic; it mirrors what the native Viewpoint Vista API returns.

## Native endpoint

Through the native Viewpoint Vista API, this operation is `POST v1/direct/subscribers/{{credentials.subscriberCode}}/vista/po/2/data/co_batch_entries/actions/add` (base URL `https://api.xchange.trimble.com/connect/`). The Universal API call above is translated to it by MindCloud, including authentication. See the [native action reference](../../native-api/actions/add-change-order-batch-entry.md) for the provider-specific parameters and requirements.

