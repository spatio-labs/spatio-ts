
# ValidateKeyBindingRequest


## Properties

Name | Type
------------ | -------------
`actionId` | string
`key` | string
`modifiers` | Array&lt;string&gt;

## Example

```typescript
import type { ValidateKeyBindingRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "actionId": null,
  "key": null,
  "modifiers": null,
} satisfies ValidateKeyBindingRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ValidateKeyBindingRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


