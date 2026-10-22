# Add Change Order Batch Entry with Viewpoint Vista

## Endpoint

- **Method:** `POST`
- **Path:** `v1/direct/subscribers/{subscriberCode}/vista/po/2/data/co_batch_entries/actions/add`
- **Base URL:** `https://api.xchange.trimble.com/connect/`
- **API:** REST
- **Official documentation:** [Add Change Order Batch Entry](https://direct-api.xchange.trimble.com/reference/post-directsubscriberssubscriber_codevistapo2dataco_batch_entriesactionsadd)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `Co` | body | `number` | yes | Company. Key to the change order batch. |
| `Mth` | body | `string` | yes | Batch posting month in YYYY-MM-01 format. |
| `BatchId` | body | `number` | yes | Change order batch ID. |
| `POCONum` | body | `number` | no | Optional PO change order number; the next available number is used when omitted. |
| `ChangeOrder` | body | `string` | no | Optional change order number used to group related changes. |
| `ActDate` | body | `string` | no | Optional action date in YYYY-MM-DD format. |
| `PO` | body | `string` | yes | Purchase order number. |
| `POItem` | body | `number` | yes | Purchase order line item number. |
| `Description` | body | `string` | no | Optional change description. |
| `ChangeCurUnits` | body | `string` | no | Optional change to current units for non-LS items. |
| `ChangeBOUnits` | body | `string` | no | Optional change to backorder units for non-LS items. |
| `ChangeCurCost` | body | `string` | no | Optional change to current cost for LS items. |
| `ChangeBOCost` | body | `string` | no | Optional change to backorder cost for LS items. |
| `NewLineItem` | body | `object` | no | Optional details used when adding a new PO line item. |
| `NewLineItem.ItemType` | body | `list<number>` | no | Required only when adding a new purchase order line. 1: Job; 2: Inventory; 3: Expense; 4: Equipment; 5: EM Work Order; 6: SM Work Order. Leave all New Line Item fields empty for an existing line. Accepted values: `1`, `2`, `3`, `4`, `5`, `6`. |
| `NewLineItem.Description` | body | `string` | no | Optional.  if omitted, null will be defaulted. Maximum length: 60. |
| `NewLineItem.JCCo` | body | `number` | no | Required when adding a new line with item type 1. Used for item type 1. Key to jc/jobs(JCCo, Job). |
| `NewLineItem.Job` | body | `string` | no | Required when adding a new line with item type 1. Used for item type 1. Key to jc/jobs(JCCo, Job). Maximum length: 10. |
| `NewLineItem.Phase` | body | `string` | no | Used for item type 1. Key to jc/job_phases(JCCo, Job, PhaseGroup, Phase)  The PhaseGroup will be selected based on the JCCo value.  Optional.  If omitted, it will be defaulted based on Vista defaulting logic.  If a default cannot be applied, this action may fail or force a Vista user to supply this value before posting. Maximum length: 20. |
| `NewLineItem.JCCType` | body | `number` | no | Used for item type 1. Key to CostTypes array in jc/job_phases(JCCo, Job, PhaseGroup, Phase, $.CostTypes.CostType)  Optional.  If omitted, it will be defaulted based on Vista defaulting logic.  If a default cannot be applied, this action may fail or  force a Vista user to supply this value before posting. |
| `NewLineItem.GLAcct` | body | `string` | no | GL account. Optional; company selection and defaults depend on Item Type and Vista configuration. Some item types disallow account overrides. Maximum length: 20. |
| `NewLineItem.Material` | body | `string` | no | Material code. Required for Inventory (Item Type 2); optional for other types. Material group is resolved from the applicable company. Maximum length: 20. |
| `NewLineItem.VendMatId` | body | `string` | no | Key to po/vendor_materials(VendorGroup, Vendor, MaterlGroup, Material, UM).  Vendor's Material Number. Optional.  If Omitted, it will be defaulted based Vista defaulting behavior. Maximum length: 30. |
| `NewLineItem.RecvYN` | body | `list<string>` | no | Receiving in PO Module.  Optional.  If omitted, N will be defaulted.  Send Y if this item will be received in the PO module. Accepted values: `N`, `Y`. |
| `NewLineItem.ReqDate` | body | `date` | no | Required Date.  Format: YYYY-MM-DD.  Optional.  If not provided it will be defaulted to $.ExpDate. |
| `NewLineItem.PayCategory` | body | `number` | no | Key to ap/pay_categories(APCo, PayCategory).  APCo will be defaulted based on Vista defaulting logic.  Optional.  If omitted, it will be defaulted based on Vista defaulting behavior.  In some configurations, overrides are not allowed.  Providing this property when overrides are not allowed will result in an error. |
| `NewLineItem.PayType` | body | `number` | no | Key to ap/pay_categories(APCo, PayCategory).  APCo will be defaulted based on Vista defaulting logic.  Optional.  If omitted Vista defaulted based on Vista defaulting behavior.  In some configurations, overrides are not allowed.  Providing this property when overrides are not allowed will result in an error.  In all cases if PayCategory is provided or defaulted this value must be in the PayCategory or in no PayCategory |
| `NewLineItem.Amount` | body | `object` | no | If omitted, each property will be defaulted as noted on each property. |
| `NewLineItem.Amount.UM` | body | `string` | no | Key to hq/units_of_measures(UM).  Optional. If omitted, it will be defaulted based on Vista defaulting behavior. Maximum length: 3. |
| `NewLineItem.Amount.OrigUnitCost` | body | `string` | no | Optional. If omitted, it will be defaulted based on Vista defaulting logic.  If UM is LS, this value is ignored and will be set to 0. |
| `NewLineItem.Amount.OrigECM` | body | `list<string>` | no | Options: E-CostPerEach, C-CostPer100, M-CostPer1000.  Optional. If omitted, it will be defaulted based on Vista defaulting behavior.  If UM is LS, this value is ignored and will be set to null. Accepted values: `C`, `E`, `M`, `null`. Maximum length: 1. |
| `NewLineItem.Tax` | body | `object` | no | Optional.  If omitted each property will be be defaulted based on Vista defaulting behavior. |
| `NewLineItem.Tax.TaxType` | body | `list<number>` | no | Options: 1-Sales, 2-Use, 3-VAT.  Optional.  If not provided, it will be defaulted based on Vista defaulting behavior. Accepted values: `1`, `2`, `3`. |
| `NewLineItem.Tax.TaxCode` | body | `string` | no | Key to hq/tax_codes(TaxGroup, TaxCode).  TaxGroup will be determined based on JCCo.  Optional.  If not provided, it will be defaulted based on Vista defaulting behavior. Maximum length: 10. |
| `NewLineItem.Supplier` | body | `number` | no | Key to ap/vendors(SupplierGroup, Supplier) for supplier for this line.  SupplierGroup is defaulted based on Co.  Optional.  If omitted, null will be defaulted. |
| `NewLineItem.Notes` | body | `string` | no | Optional.  If not provided, null will be defaulted. |
| `NewLineItem.__custom_fields` | body | `object` | no | Add a property to this object for each user defined field to be set.  Property name set to the user defined field name. |
| `NewLineItem.INCo` | body | `number` | no | Required when adding a new line with item type 2. Used for item type 2. Key to in/locations(INCo, Loc). |
| `NewLineItem.Loc` | body | `string` | no | Required when adding a new line with item type 2. Used for item type 2. Key to in/locations(INCo, Loc). Maximum length: 10. |
| `NewLineItem.GLCo` | body | `number` | no | Required when adding a new line with item type 3. Used for item type 3. Key to gl/chart_of_accounts(GLCo, GLAcct). |
| `NewLineItem.EMCo` | body | `number` | no | Equipment company. Required for Equipment (4) and EM Work Order (5). |
| `NewLineItem.Equip` | body | `string` | no | Required when adding a new line with item type 4. Used for item type 4. Key to em/equipment(EMCo, Equipment). Maximum length: 10. |
| `NewLineItem.CompType` | body | `string` | no | Used for item type 4. Optional.  If omitted, null will be defaulted. Maximum length: 10. |
| `NewLineItem.Component` | body | `string` | no | Used for item type 4. Optional.  If omitted, null will be defaulted. Maximum length: 10. |
| `NewLineItem.CostCode` | body | `string` | no | Equipment cost code. Required for Equipment (4); for EM Work Order (5), may be ignored when specified by the work order item. Maximum length: 10. |
| `NewLineItem.EMCType` | body | `number` | no | Required when adding a new line with item type 4, 5. Used for item type 4, 5. key to CostTypes array in em/cost_codes(EMGroup, CostCode, $.CostTypes.CostType). |
| `NewLineItem.WO` | body | `string` | no | Required when adding a new line with item type 5. Used for item type 5. Equipment Work Order. Maximum length: 10. |
| `NewLineItem.WOItem` | body | `number` | no | Required when adding a new line with item type 5. Used for item type 5. Equipment Work Order Item. |
| `NewLineItem.SMCo` | body | `number` | no | Required when adding a new line with item type 6. Used for item type 6. SM Company. |
| `NewLineItem.SMWorkOrder` | body | `number` | no | Required when adding a new line with item type 6. Used for item type 6. SM Work Order |
| `NewLineItem.SMScope` | body | `number` | no | Required when adding a new line with item type 6. Used for item type 6. SM Scope |
| `NewLineItem.SMCostType` | body | `number` | no | Required when adding a new line with item type 6. Used for item type 6. SM Cost Type. |
| `NewLineItem.SMPhase` | body | `string` | no | Used for item type 6. Key to jc/job_phases(SMPhaseGroup, SMPhase).  SMPhaseGroup will be defaulted based on the JCCo associated to the SM Work Order.  Optional.  This value should only be supplied if the SM Scope does not have a Phase assigned. Maximum length: 20. |
| `NewLineItem.SMJCCostType` | body | `number` | no | Used for item type 6. Key to CostTypes array in jc/job_phases(JCCo, Job, PhaseGroup, Phase, $.CostTypes.CostType)  Optional.  This value should only be supplied if the SM Scope does not have a CostType assigned. |
| `Notes` | body | `string` | no | Optional entry notes. |
| `__custom_fields` | body | `object` | no | Optional Vista user-defined fields, keyed by field name. |
