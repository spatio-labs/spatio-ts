
# UserInfoResponse


## Properties

Name | Type
------------ | -------------
`sub` | string
`email` | string
`email_verified` | boolean
`name` | string
`given_name` | string
`family_name` | string
`preferred_username` | string
`picture` | string
`updated_at` | number

## Example

```typescript
import type { UserInfoResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "sub": null,
  "email": null,
  "email_verified": null,
  "name": null,
  "given_name": null,
  "family_name": null,
  "preferred_username": null,
  "picture": null,
  "updated_at": null,
} satisfies UserInfoResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UserInfoResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


