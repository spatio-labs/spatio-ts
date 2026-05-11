
# UpdateConversationRequest


## Properties

Name | Type
------------ | -------------
`title` | string
`context` | string
`cwd` | string
`session_id` | string
`pinned` | boolean

## Example

```typescript
import type { UpdateConversationRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "title": null,
  "context": null,
  "cwd": null,
  "session_id": null,
  "pinned": null,
} satisfies UpdateConversationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateConversationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


