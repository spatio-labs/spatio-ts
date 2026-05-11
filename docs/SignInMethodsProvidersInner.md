
# SignInMethodsProvidersInner


## Properties

Name | Type
------------ | -------------
`provider` | string
`accountEmail` | string
`linkedAt` | Date
`lastUsedAt` | Date

## Example

```typescript
import type { SignInMethodsProvidersInner } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "accountEmail": null,
  "linkedAt": null,
  "lastUsedAt": null,
} satisfies SignInMethodsProvidersInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SignInMethodsProvidersInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


