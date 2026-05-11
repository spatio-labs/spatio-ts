
# BulkMarkReadResponse

Partial-success envelope for `bulkMarkEmailsRead`. `updated` is a count (not an array — distinct from archive/delete which return the actual id list). The failed-row shape uses `id` (also distinct — renderer-compat legacy). 

## Properties

Name | Type
------------ | -------------
`updated` | number
`failed` | [Array&lt;BulkMarkReadResponseFailedInner&gt;](BulkMarkReadResponseFailedInner.md)

## Example

```typescript
import type { BulkMarkReadResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "updated": null,
  "failed": null,
} satisfies BulkMarkReadResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkMarkReadResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


