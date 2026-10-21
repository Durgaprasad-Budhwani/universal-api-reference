# List Worker Additional Remunerations with ADP

## Endpoint

- **Method:** `GET`
- **Path:** `hr/worker-profile/v1/workers/:aoid/work-assignments/:assignmentId/additional-remunerations`
- **Base URL:** `https://api.adp.com/`
- **Official documentation:** [List Worker Additional Remunerations](https://developers.adp.com/apis/api-explorer/hcm-offrg-wfn/hcm-offrg-wfn-hr-hr-worker-profiles-v1-hr-worker-profiles?operation=GET%2Fhr%2Fworker-profile%2Fv1%2Fworkers%2F%7Baoid%7D%2Fwork-assignments%2F%7Bassignment-id%7D%2Fadditional-remunerations%2Fmeta#swagger)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `aoid` | path | `string` | yes | The ADP associate object identifier for the worker whose payroll instructions should be returned. |
| `assignmentId` | path | `string` | yes | The ID of the worker's work assignment. Find it in the worker record returned by Get Worker or List Workers, in workAssignments[].itemID. Choose the work assignment whose compensation information you want to retrieve. |
