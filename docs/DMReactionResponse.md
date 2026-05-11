
# DMReactionResponse

`reactions` shape is provider-specific; treat as opaque.

## Properties

Name | Type
------------ | -------------
`reactions` | any

## Example

```typescript
import type { DMReactionResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "reactions": null,
} satisfies DMReactionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as DMReactionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


