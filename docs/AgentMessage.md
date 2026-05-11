
# AgentMessage


## Properties

Name | Type
------------ | -------------
`id` | string
`conversationId` | string
`role` | string
`content` | string
`metadata` | { [key: string]: any; }
`createdAt` | Date

## Example

```typescript
import type { AgentMessage } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "conversationId": null,
  "role": null,
  "content": null,
  "metadata": null,
  "createdAt": null,
} satisfies AgentMessage

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentMessage
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


