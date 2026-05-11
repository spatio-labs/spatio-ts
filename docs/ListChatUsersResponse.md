
# ListChatUsersResponse


## Properties

Name | Type
------------ | -------------
`users` | [Array&lt;ChatUser&gt;](ChatUser.md)
`total` | number
`nextCursor` | string
`provider` | string

## Example

```typescript
import type { ListChatUsersResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "users": null,
  "total": null,
  "nextCursor": null,
  "provider": null,
} satisfies ListChatUsersResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListChatUsersResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


