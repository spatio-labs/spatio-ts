
# BulkDeleteFilesRequest

Either `fileIds` (with optional parallel `accountIds`) for multi-file delete, or `fileId` (with optional `accountId`) for the single-file fallback. `fileIds` wins when both are set. 

## Properties

Name | Type
------------ | -------------
`fileIds` | Array&lt;string&gt;
`accountIds` | Array&lt;string&gt;
`fileId` | string
`accountId` | string

## Example

```typescript
import type { BulkDeleteFilesRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "fileIds": null,
  "accountIds": null,
  "fileId": null,
  "accountId": null,
} satisfies BulkDeleteFilesRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkDeleteFilesRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


