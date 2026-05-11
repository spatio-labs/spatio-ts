
# WorkspaceListResponse


## Properties

Name | Type
------------ | -------------
`workspaces` | [Array&lt;Workspace&gt;](Workspace.md)
`total` | number

## Example

```typescript
import type { WorkspaceListResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "workspaces": null,
  "total": null,
} satisfies WorkspaceListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WorkspaceListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


