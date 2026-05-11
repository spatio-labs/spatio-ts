
# CreateWorkspaceRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`slug` | string
`description` | string
`organizationId` | string

## Example

```typescript
import type { CreateWorkspaceRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "name": null,
  "slug": null,
  "description": null,
  "organizationId": null,
} satisfies CreateWorkspaceRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateWorkspaceRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


