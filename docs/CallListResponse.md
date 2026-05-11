
# CallListResponse


## Properties

Name | Type
------------ | -------------
`calls` | [Array&lt;SpatioCall&gt;](SpatioCall.md)
`total` | number

## Example

```typescript
import type { CallListResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "calls": null,
  "total": null,
} satisfies CallListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CallListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


