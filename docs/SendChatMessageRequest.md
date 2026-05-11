
# SendChatMessageRequest


## Properties

Name | Type
------------ | -------------
`accountId` | string
`channel` | string
`text` | string
`threadId` | string
`blocks` | Array&lt;{ [key: string]: any; }&gt;

## Example

```typescript
import type { SendChatMessageRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "channel": null,
  "text": null,
  "threadId": null,
  "blocks": null,
} satisfies SendChatMessageRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SendChatMessageRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


