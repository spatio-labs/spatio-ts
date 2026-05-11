
# BulkDeleteTasksResponse

Partial-success envelope. `success` is `true` only when zero failures; `affectedCount` is the deleted count; `taskIds` lists the ids that succeeded; `failed` lists per-id errors. 

## Properties

Name | Type
------------ | -------------
`success` | boolean
`affectedCount` | number
`taskIds` | Array&lt;string&gt;
`failed` | [Array&lt;BulkDeleteTasksResponseFailedInner&gt;](BulkDeleteTasksResponseFailedInner.md)

## Example

```typescript
import type { BulkDeleteTasksResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "affectedCount": null,
  "taskIds": null,
  "failed": null,
} satisfies BulkDeleteTasksResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkDeleteTasksResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


