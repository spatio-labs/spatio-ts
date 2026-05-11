
# WorkspaceMember


## Properties

Name | Type
------------ | -------------
`id` | string
`role` | string
`email` | string
`name` | string
`avatar` | string
`joinedAt` | Date
`user` | { [key: string]: any; }

## Example

```typescript
import type { WorkspaceMember } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "role": null,
  "email": null,
  "name": null,
  "avatar": null,
  "joinedAt": null,
  "user": null,
} satisfies WorkspaceMember

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WorkspaceMember
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


