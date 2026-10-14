# Append Media Upload with X

## Endpoint

- **Method:** `POST`
- **Path:** `/2/media/upload/:id/append`
- **Base URL:** `https://api.x.com`
- **Official documentation:** [Append Media Upload](https://docs.x.com/x-api/media/append-media-upload)

## Headers

Send these additional headers for this operation:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/json` |

## Parameters

| Parameter | Location | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `id` | path | `string` | yes | Media ID returned by Initialize Media Upload. |
| `media` | body | `string` | yes | Base64-encoded chunk contents for JSON upload. |
| `segment_index` | body | `number` | yes | Zero-based chunk index, 0–9999. |
