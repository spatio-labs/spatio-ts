
# OrganizationMember


## Properties

Name | Type
------------ | -------------
`id` | string
`userId` | string
`role` | string
`joinedAt` | Date
`invitedBy` | [OrganizationMemberInvitedBy](OrganizationMemberInvitedBy.md)
`user` | { [key: string]: any; }

## Example

```typescript
import type { OrganizationMember } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "userId": null,
  "role": null,
  "joinedAt": null,
  "invitedBy": null,
  "user": null,
} satisfies OrganizationMember

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OrganizationMember
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


