
# OrganizationInvitation


## Properties

Name | Type
------------ | -------------
`id` | string
`organizationId` | string
`email` | string
`role` | string
`token` | string
`expiresAt` | Date
`createdAt` | Date
`acceptedAt` | Date
`revokedAt` | Date
`invitedBy` | [OrganizationMemberInvitedBy](OrganizationMemberInvitedBy.md)
`status` | string

## Example

```typescript
import type { OrganizationInvitation } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "organizationId": null,
  "email": null,
  "role": null,
  "token": null,
  "expiresAt": null,
  "createdAt": null,
  "acceptedAt": null,
  "revokedAt": null,
  "invitedBy": null,
  "status": null,
} satisfies OrganizationInvitation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OrganizationInvitation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


