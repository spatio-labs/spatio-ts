
# OrganizationMemberListResponse


## Properties

Name | Type
------------ | -------------
`members` | [Array&lt;OrganizationMember&gt;](OrganizationMember.md)
`total` | number

## Example

```typescript
import type { OrganizationMemberListResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "members": null,
  "total": null,
} satisfies OrganizationMemberListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OrganizationMemberListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


