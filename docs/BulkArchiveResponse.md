
# BulkArchiveResponse

Partial-success envelope for `bulkArchiveEmails`.

## Properties

Name | Type
------------ | -------------
`success` | boolean
`archived` | Array&lt;string&gt;
`failed` | [Array&lt;BulkArchiveResponseFailedInner&gt;](BulkArchiveResponseFailedInner.md)

## Example

```typescript
import type { BulkArchiveResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "archived": null,
  "failed": null,
} satisfies BulkArchiveResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkArchiveResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


