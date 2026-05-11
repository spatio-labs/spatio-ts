
# CreateAgentMessageRequest


## Properties

Name | Type
------------ | -------------
`role` | string
`content` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CreateAgentMessageRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "role": null,
  "content": null,
  "metadata": null,
} satisfies CreateAgentMessageRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAgentMessageRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


