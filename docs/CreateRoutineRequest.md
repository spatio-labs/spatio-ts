
# CreateRoutineRequest


## Properties

Name | Type
------------ | -------------
`workspaceId` | string
`name` | string
`description` | string
`schedule` | { [key: string]: any; }
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CreateRoutineRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "workspaceId": null,
  "name": null,
  "description": null,
  "schedule": null,
  "metadata": null,
} satisfies CreateRoutineRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateRoutineRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


