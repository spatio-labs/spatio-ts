
# PublicInvitationPayload

Returned by `GET /invitations/{token}` (unauthenticated). Lets the renderer show invitation details (workspace name, inviter, role) before the user signs in. 

## Properties

Name | Type
------------ | -------------
`kind` | string
`id` | string
`workspaceId` | string
`organizationId` | string
`email` | string
`role` | string
`status` | string
`expiresAt` | Date
`createdAt` | Date
`workspace` | { [key: string]: any; }
`organization` | { [key: string]: any; }
`invitedBy` | { [key: string]: any; }

## Example

```typescript
import type { PublicInvitationPayload } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "kind": null,
  "id": null,
  "workspaceId": null,
  "organizationId": null,
  "email": null,
  "role": null,
  "status": null,
  "expiresAt": null,
  "createdAt": null,
  "workspace": null,
  "organization": null,
  "invitedBy": null,
} satisfies PublicInvitationPayload

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PublicInvitationPayload
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


