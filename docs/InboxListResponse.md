
# InboxListResponse


## Properties

Name | Type
------------ | -------------
`items` | [Array&lt;InboxItem&gt;](InboxItem.md)
`totalCount` | number
`hasMore` | boolean

## Example

```typescript
import type { InboxListResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "items": null,
  "totalCount": null,
  "hasMore": null,
} satisfies InboxListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboxListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


