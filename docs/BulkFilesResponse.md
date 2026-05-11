
# BulkFilesResponse

Partial-success envelope for bulk delete/move.

## Properties

Name | Type
------------ | -------------
`success` | boolean
`affectedCount` | number
`fileIds` | Array&lt;string&gt;
`failed` | [Array&lt;BulkFilesResponseFailedInner&gt;](BulkFilesResponseFailedInner.md)

## Example

```typescript
import type { BulkFilesResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "affectedCount": null,
  "fileIds": null,
  "failed": null,
} satisfies BulkFilesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkFilesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


