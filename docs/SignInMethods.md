
# SignInMethods


## Properties

Name | Type
------------ | -------------
`email` | string
`hasPassword` | boolean
`providers` | [Array&lt;SignInMethodsProvidersInner&gt;](SignInMethodsProvidersInner.md)

## Example

```typescript
import type { SignInMethods } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "email": null,
  "hasPassword": null,
  "providers": null,
} satisfies SignInMethods

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SignInMethods
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


