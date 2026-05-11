
# InitChunkedUploadRequest


## Properties

Name | Type
------------ | -------------
`fileName` | string
`totalSize` | number
`mimeType` | string
`expectedBlocks` | Array&lt;string&gt;
`folderId` | string
`workspaceId` | string
`organizationId` | string

## Example

```typescript
import type { InitChunkedUploadRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "fileName": null,
  "totalSize": null,
  "mimeType": null,
  "expectedBlocks": null,
  "folderId": null,
  "workspaceId": null,
  "organizationId": null,
} satisfies InitChunkedUploadRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InitChunkedUploadRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


