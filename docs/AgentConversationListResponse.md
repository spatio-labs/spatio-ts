
# AgentConversationListResponse


## Properties

Name | Type
------------ | -------------
`conversations` | [Array&lt;AgentConversation&gt;](AgentConversation.md)
`total` | number

## Example

```typescript
import type { AgentConversationListResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "conversations": null,
  "total": null,
} satisfies AgentConversationListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentConversationListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


