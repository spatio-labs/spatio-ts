
# AmbiguousAccountError

Returned when the caller\'s request matches more than one connected account and no `accountId` query param disambiguates which one to target. The `accounts` array enumerates the candidates so the client can prompt the user to pick. 

## Properties

Name | Type
------------ | -------------
`error` | string
`code` | string
`accounts` | [Array&lt;AccountChoice&gt;](AccountChoice.md)

## Example

```typescript
import type { AmbiguousAccountError } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "error": user not authenticated,
  "code": ambiguous_account,
  "accounts": null,
} satisfies AmbiguousAccountError

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AmbiguousAccountError
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


