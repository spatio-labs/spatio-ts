
# CommitChunkedUploadResponse


## Properties

Name | Type
------------ | -------------
`success` | boolean
`fileId` | string
`manifestId` | string
`version` | number
`totalSize` | number
`physicalSize` | number
`deduplicationPct` | number
`totalBlocks` | number
`newBlocks` | number
`deduplicatedBlocks` | number

## Example

```typescript
import type { CommitChunkedUploadResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "fileId": null,
  "manifestId": null,
  "version": null,
  "totalSize": null,
  "physicalSize": null,
  "deduplicationPct": null,
  "totalBlocks": null,
  "newBlocks": null,
  "deduplicatedBlocks": null,
} satisfies CommitChunkedUploadResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CommitChunkedUploadResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


