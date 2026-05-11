
# BulkMoveFilesRequest

Move multiple files to one target folder. `targetFolderId` is the canonical name; `folderId` is accepted as a renderer-compat alias. 

## Properties

Name | Type
------------ | -------------
`fileIds` | Array&lt;string&gt;
`accountIds` | Array&lt;string&gt;
`accountId` | string
`targetFolderId` | string
`folderId` | string

## Example

```typescript
import type { BulkMoveFilesRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "fileIds": null,
  "accountIds": null,
  "accountId": null,
  "targetFolderId": null,
  "folderId": null,
} satisfies BulkMoveFilesRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkMoveFilesRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


