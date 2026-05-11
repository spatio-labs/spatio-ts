
# BulkDeleteEmailsResponse

Partial-success envelope for `bulkDeleteEmails`.

## Properties

Name | Type
------------ | -------------
`success` | boolean
`deleted` | Array&lt;string&gt;
`failed` | [Array&lt;BulkArchiveResponseFailedInner&gt;](BulkArchiveResponseFailedInner.md)

## Example

```typescript
import type { BulkDeleteEmailsResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "deleted": null,
  "failed": null,
} satisfies BulkDeleteEmailsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkDeleteEmailsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


