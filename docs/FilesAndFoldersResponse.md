
# FilesAndFoldersResponse

Aggregated `{files, folders, accounts}` envelope used by the renderer\'s file-browser. Calls `ListFiles` and `ListFolders` in parallel and merges the results — saves a round-trip when the UI shows both side-by-side. 

## Properties

Name | Type
------------ | -------------
`files` | [Array&lt;SpatioFile&gt;](SpatioFile.md)
`folders` | [Array&lt;Folder&gt;](Folder.md)
`accounts` | [Array&lt;AccountStatus&gt;](AccountStatus.md)
`total` | number
`hasMore` | boolean
`nextOffset` | number

## Example

```typescript
import type { FilesAndFoldersResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "files": null,
  "folders": null,
  "accounts": null,
  "total": null,
  "hasMore": null,
  "nextOffset": null,
} satisfies FilesAndFoldersResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as FilesAndFoldersResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


