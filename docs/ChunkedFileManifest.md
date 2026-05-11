
# ChunkedFileManifest

Block-level manifest for a chunked-uploaded file. Returned by `GET /v1/files/{id}/manifest`. Only meaningful for files uploaded via the chunked path; legacy uploads return `404`. 

## Properties

Name | Type
------------ | -------------
`manifestId` | string
`fileId` | string
`fileName` | string
`version` | number
`totalSize` | number
`blockCount` | number
`chunkingAlgorithm` | string
`fileChecksum` | string
`blocks` | Array&lt;{ [key: string]: any; }&gt;

## Example

```typescript
import type { ChunkedFileManifest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "manifestId": null,
  "fileId": null,
  "fileName": null,
  "version": null,
  "totalSize": null,
  "blockCount": null,
  "chunkingAlgorithm": null,
  "fileChecksum": null,
  "blocks": null,
} satisfies ChunkedFileManifest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ChunkedFileManifest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


