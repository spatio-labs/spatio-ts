
# PersonalAccessToken


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`scopes` | Array&lt;string&gt;
`workspaceId` | string
`createdAt` | Date
`lastUsedAt` | Date
`expiresAt` | Date
`tokenPrefix` | string

## Example

```typescript
import type { PersonalAccessToken } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "scopes": null,
  "workspaceId": null,
  "createdAt": null,
  "lastUsedAt": null,
  "expiresAt": null,
  "tokenPrefix": null,
} satisfies PersonalAccessToken

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PersonalAccessToken
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


