
# BulkUpdateTasksResponse


## Properties

Name | Type
------------ | -------------
`success` | boolean
`affectedCount` | number
`tasks` | [Array&lt;Task&gt;](Task.md)
`failed` | [Array&lt;BulkDeleteTasksResponseFailedInner&gt;](BulkDeleteTasksResponseFailedInner.md)

## Example

```typescript
import type { BulkUpdateTasksResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "affectedCount": null,
  "tasks": null,
  "failed": null,
} satisfies BulkUpdateTasksResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkUpdateTasksResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


