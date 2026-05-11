
# Workspace

A workspace within an organization. Returned in list responses (`GET /v1/workspaces`, `GET /v1/organizations/{id}/workspaces`) and the single-get response (`GET /v1/workspaces/{id}`, wrapped in `{workspace: ...}`).  `settings` shape varies by endpoint — sometimes a JSON object, sometimes a JSON-encoded string. Treat as opaque. 

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`slug` | string
`description` | string
`logoUrl` | string
`organizationId` | string
`organization` | [WorkspaceOrganization](WorkspaceOrganization.md)
`role` | string
`settings` | any
`isDefault` | boolean
`memberCount` | number
`billingTier` | string
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { Workspace } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "slug": null,
  "description": null,
  "logoUrl": null,
  "organizationId": null,
  "organization": null,
  "role": null,
  "settings": null,
  "isDefault": null,
  "memberCount": null,
  "billingTier": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies Workspace

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Workspace
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


