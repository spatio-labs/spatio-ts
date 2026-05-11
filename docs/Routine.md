
# Routine


## Properties

Name | Type
------------ | -------------
`id` | string
`workspaceId` | string
`name` | string
`description` | string
`schedule` | { [key: string]: any; }
`status` | string
`metadata` | { [key: string]: any; }
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { Routine } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "workspaceId": null,
  "name": null,
  "description": null,
  "schedule": null,
  "status": null,
  "metadata": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies Routine

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Routine
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


