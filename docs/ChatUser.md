
# ChatUser


## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`name` | string
`realName` | string
`email` | string
`avatar` | string
`isBot` | boolean
`isActive` | boolean

## Example

```typescript
import type { ChatUser } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "name": null,
  "realName": null,
  "email": null,
  "avatar": null,
  "isBot": null,
  "isActive": null,
} satisfies ChatUser

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ChatUser
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


