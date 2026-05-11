
# ConversationMessage


## Properties

Name | Type
------------ | -------------
`id` | string
`conversation_id` | string
`role` | string
`content` | string
`metadata` | { [key: string]: any; }
`created_at` | Date

## Example

```typescript
import type { ConversationMessage } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "conversation_id": null,
  "role": null,
  "content": null,
  "metadata": null,
  "created_at": null,
} satisfies ConversationMessage

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ConversationMessage
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


