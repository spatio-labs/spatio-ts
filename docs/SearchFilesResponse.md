
# SearchFilesResponse

In-memory substring search across the caller\'s files. Provider filtering isn\'t standardized across providers, so the platform lists up to ~500 files and filters locally — `total` is the pre-truncation count, not the global count. 

## Properties

Name | Type
------------ | -------------
`files` | [Array&lt;SpatioFile&gt;](SpatioFile.md)
`total` | number
`hasMore` | boolean
`query` | string

## Example

```typescript
import type { SearchFilesResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "files": null,
  "total": null,
  "hasMore": null,
  "query": null,
} satisfies SearchFilesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchFilesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


