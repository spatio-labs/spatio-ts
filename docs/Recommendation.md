
# Recommendation

Agent-authored proposal that surfaces on the home feed. Status transitions: `pending` → `accepted | dismissed | expired`. 

## Properties

Name | Type
------------ | -------------
`id` | string
`workspaceId` | string
`userId` | string
`kind` | string
`title` | string
`body` | string
`status` | string
`payload` | { [key: string]: any; }
`createdAt` | Date
`updatedAt` | Date
`expiresAt` | Date

## Example

```typescript
import type { Recommendation } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "workspaceId": null,
  "userId": null,
  "kind": null,
  "title": null,
  "body": null,
  "status": null,
  "payload": null,
  "createdAt": null,
  "updatedAt": null,
  "expiresAt": null,
} satisfies Recommendation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Recommendation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


