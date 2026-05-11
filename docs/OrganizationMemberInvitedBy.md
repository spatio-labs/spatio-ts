
# OrganizationMemberInvitedBy

Inviter info. Returns either a bare user id (`string`) on legacy paths, or an object envelope `{id, email, name, ...}` on enriched responses. Treat as opaque. 

## Properties

Name | Type
------------ | -------------

## Example

```typescript
import type { OrganizationMemberInvitedBy } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
} satisfies OrganizationMemberInvitedBy

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OrganizationMemberInvitedBy
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


