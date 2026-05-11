
# Organization

Organization summary used in list responses (`GET /v1/organizations`, `GET /v1/organizations/{id}/workspaces`). Returned with camelCase field names.  NB: The single-org GET `/v1/organizations/{id}` returns a *different shape* (`OrganizationDetailLegacy`, PascalCase keys) today — see that schema for the wire-level reality. This is a known inconsistency the platform-service is expected to converge on the camelCase shape in a future cleanup. 

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`slug` | string
`description` | string
`logoUrl` | string
`role` | string
`memberCount` | number
`workspaceCount` | number
`workspaces` | [Array&lt;OrganizationWorkspacesInner&gt;](OrganizationWorkspacesInner.md)
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { Organization } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "slug": null,
  "description": null,
  "logoUrl": null,
  "role": null,
  "memberCount": null,
  "workspaceCount": null,
  "workspaces": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies Organization

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Organization
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


