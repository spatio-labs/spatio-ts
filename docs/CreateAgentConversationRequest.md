
# CreateAgentConversationRequest


## Properties

Name | Type
------------ | -------------
`agentId` | string
`title` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CreateAgentConversationRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "agentId": null,
  "title": null,
  "metadata": null,
} satisfies CreateAgentConversationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAgentConversationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


