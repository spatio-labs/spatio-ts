
# WorkspaceInvitation


## Properties

Name | Type
------------ | -------------
`id` | string
`workspaceId` | string
`email` | string
`role` | string
`expiresAt` | Date
`createdAt` | Date
`acceptedAt` | Date
`revokedAt` | Date
`status` | string

## Example

```typescript
import type { WorkspaceInvitation } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "workspaceId": null,
  "email": null,
  "role": null,
  "expiresAt": null,
  "createdAt": null,
  "acceptedAt": null,
  "revokedAt": null,
  "status": null,
} satisfies WorkspaceInvitation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WorkspaceInvitation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


