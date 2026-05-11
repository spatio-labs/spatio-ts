
# Conversation

LLM conversation persisted by the platform-service. Stored in snake_case at the wire (legacy DTO; predates the camelCase rest of the API). Treat field names as authoritative. 

## Properties

Name | Type
------------ | -------------
`id` | string
`user_id` | string
`title` | string
`context` | string
`cwd` | string
`session_id` | string
`pinned` | boolean
`last_message_at` | Date
`message_count` | number
`is_active` | boolean
`metadata` | { [key: string]: any; }
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { Conversation } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "user_id": null,
  "title": null,
  "context": null,
  "cwd": null,
  "session_id": null,
  "pinned": null,
  "last_message_at": null,
  "message_count": null,
  "is_active": null,
  "metadata": null,
  "created_at": null,
  "updated_at": null,
} satisfies Conversation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Conversation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


