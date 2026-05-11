
# PasswordRequiredError

Returned by `GET /public/notes/{token}` when the note is password-protected. `requiresPassword` is always `true` in this response; `invalidPassword` is `true` only when a password was supplied and rejected. 

## Properties

Name | Type
------------ | -------------
`error` | string
`code` | string
`requiresPassword` | boolean
`invalidPassword` | boolean

## Example

```typescript
import type { PasswordRequiredError } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "error": user not authenticated,
  "code": ambiguous_account,
  "requiresPassword": null,
  "invalidPassword": null,
} satisfies PasswordRequiredError

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PasswordRequiredError
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


