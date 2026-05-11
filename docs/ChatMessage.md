
# ChatMessage


## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`channelId` | string
`userId` | string
`text` | string
`threadId` | string
`timestamp` | Date
`replyCount` | number
`extra` | { [key: string]: any; }

## Example

```typescript
import type { ChatMessage } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "channelId": null,
  "userId": null,
  "text": null,
  "threadId": null,
  "timestamp": null,
  "replyCount": null,
  "extra": null,
} satisfies ChatMessage

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ChatMessage
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


