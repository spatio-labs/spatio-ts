
# RoutineRun


## Properties

Name | Type
------------ | -------------
`id` | string
`routineId` | string
`status` | string
`progress` | number
`metadata` | { [key: string]: any; }
`startedAt` | Date
`completedAt` | Date

## Example

```typescript
import type { RoutineRun } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "routineId": null,
  "status": null,
  "progress": null,
  "metadata": null,
  "startedAt": null,
  "completedAt": null,
} satisfies RoutineRun

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RoutineRun
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


