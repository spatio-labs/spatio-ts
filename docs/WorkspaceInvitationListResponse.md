
# WorkspaceInvitationListResponse


## Properties

Name | Type
------------ | -------------
`invitations` | [Array&lt;WorkspaceInvitation&gt;](WorkspaceInvitation.md)

## Example

```typescript
import type { WorkspaceInvitationListResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "invitations": null,
} satisfies WorkspaceInvitationListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WorkspaceInvitationListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


