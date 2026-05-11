
# AccountChoice

One of the candidates returned alongside an `ambiguous_account` error so the client can prompt the user to pick a target account. 

## Properties

Name | Type
------------ | -------------
`provider` | string
`accountId` | string
`accountName` | string

## Example

```typescript
import type { AccountChoice } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "accountId": null,
  "accountName": null,
} satisfies AccountChoice

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountChoice
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


