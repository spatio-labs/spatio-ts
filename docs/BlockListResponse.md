
# BlockListResponse

Single-account list response for `GET /v1/notes/{id}/blocks`. Unlike `GET /v1/notes`, block listing always targets one account so it does not fan out — `total` is the count for the current page slice. 

## Properties

Name | Type
------------ | -------------
`blocks` | [Array&lt;Block&gt;](Block.md)
`total` | number

## Example

```typescript
import type { BlockListResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "blocks": null,
  "total": null,
} satisfies BlockListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BlockListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


