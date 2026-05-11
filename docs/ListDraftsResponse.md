
# ListDraftsResponse


## Properties

Name | Type
------------ | -------------
`drafts` | [Array&lt;Draft&gt;](Draft.md)
`total` | number
`nextPageToken` | string
`provider` | string

## Example

```typescript
import type { ListDraftsResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "drafts": null,
  "total": null,
  "nextPageToken": null,
  "provider": null,
} satisfies ListDraftsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListDraftsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


