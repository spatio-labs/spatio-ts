
# CreateOrganizationRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`slug` | string
`description` | string
`logoUrl` | string
`createDefaultWorkspace` | boolean
`defaultWorkspaceName` | string

## Example

```typescript
import type { CreateOrganizationRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "name": null,
  "slug": null,
  "description": null,
  "logoUrl": null,
  "createDefaultWorkspace": null,
  "defaultWorkspaceName": null,
} satisfies CreateOrganizationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateOrganizationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


