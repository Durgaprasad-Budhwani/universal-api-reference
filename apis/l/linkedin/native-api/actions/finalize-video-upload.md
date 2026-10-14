# Finalize Video Upload with LinkedIn

Finalizes a video upload in LinkedIn.

## Endpoint

- **Method:** `POST`
- **Path:** `/rest/videos?action=finalizeUpload`
- **Base URL:** `https://api.linkedin.com`
- **Official documentation:** [Finalize Video Upload](https://learn.microsoft.com/en-us/linkedin/marketing/community-management/shares/videos-api?view=li-lms-2026-02)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `finalizeUploadRequest` | body | `object` | yes | — |
| `finalizeUploadRequest.video` | body | `string` | yes | — |
| `finalizeUploadRequest.uploadToken` | body | `string` | yes | — |
| `finalizeUploadRequest.uploadedPartIds[]` | body | `array<string>` | yes | Array of uploaded part IDs returned by LinkedIn upload instructions. |
