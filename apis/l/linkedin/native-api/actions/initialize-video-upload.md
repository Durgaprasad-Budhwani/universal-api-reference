# Initialize Video Upload with LinkedIn

Initializes a video upload in LinkedIn.

## Endpoint

- **Method:** `POST`
- **Path:** `/rest/videos?action=initializeUpload`
- **Base URL:** `https://api.linkedin.com`
- **Official documentation:** [Initialize Video Upload](https://learn.microsoft.com/en-us/linkedin/marketing/community-management/shares/videos-api?view=li-lms-2026-02)

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `initializeUploadRequest` | body | `object` | yes | — |
| `initializeUploadRequest.mediaLibraryMetadata.associatedAccount` | body | `string` | no | — |
| `initializeUploadRequest.owner` | body | `string` | yes | Owner URN for the member initializing the upload. |
| `initializeUploadRequest.fileSizeBytes` | body | `number` | yes | — |
| `initializeUploadRequest.mediaLibraryMetadata.assetName` | body | `string` | no | — |
| `initializeUploadRequest.mediaLibraryMetadata.mediaLibraryStatus` | body | `list<string>` | no | Accepted values: `ACTIVE`, `ARCHIVED`. |
| `initializeUploadRequest.uploadCaptions` | body | `boolean` | no | Only one English-language captions file is supported. |
| `initializeUploadRequest.uploadThumbnail` | body | `boolean` | no | Requests a thumbnail upload URL. |
| `initializeUploadRequest.templateName` | body | `string` | no | Supported with LinkedIn API version 202602 or later. |
| `initializeUploadRequest.linkbackContext` | body | `string` | no | Supported with LinkedIn API version 202602 or later. |
| `initializeUploadRequest.mediaLibraryMetadata` | body | `object` | no | — |
