
# AgentConversation

LLM conversation tracked by the agent platform (distinct from /v1/conversations which is the renderer-driven sidebar persistence). 

## Properties

Name | Type
------------ | -------------
`id` | string
`agentId` | string
`title` | string
`metadata` | { [key: string]: any; }
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { AgentConversation } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "agentId": null,
  "title": null,
  "metadata": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies AgentConversation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentConversation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


