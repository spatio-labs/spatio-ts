
# EnableShareRequest

Body for `POST /v1/notes/{id}/share`. With `setPassword: false`, only the public flag is flipped — any existing password is preserved. With `setPassword: true`, the supplied `password` is applied (an empty string clears it). 

## Properties

Name | Type
------------ | -------------
`setPassword` | boolean
`password` | string

## Example

```typescript
import type { EnableShareRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "setPassword": null,
  "password": null,
} satisfies EnableShareRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EnableShareRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


