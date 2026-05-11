
# UpdateEmailResponse


## Properties

Name | Type
------------ | -------------
`email` | [Email](Email.md)
`provider` | string

## Example

```typescript
import type { UpdateEmailResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "email": null,
  "provider": null,
} satisfies UpdateEmailResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateEmailResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


