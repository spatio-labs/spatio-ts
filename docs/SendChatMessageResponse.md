
# SendChatMessageResponse


## Properties

Name | Type
------------ | -------------
`success` | boolean
`messageId` | string
`channelId` | string
`threadId` | string
`provider` | string
`error` | string

## Example

```typescript
import type { SendChatMessageResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "messageId": null,
  "channelId": null,
  "threadId": null,
  "provider": null,
  "error": null,
} satisfies SendChatMessageResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SendChatMessageResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


