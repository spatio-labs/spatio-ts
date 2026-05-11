
# BulkDeleteTasksRequest

Either populate `taskIds` (with optional parallel `accountIds`) for multi-task delete, or `taskId` (with optional `accountId`) for the single-task fallback. `taskIds` wins when both are set. 

## Properties

Name | Type
------------ | -------------
`taskIds` | Array&lt;string&gt;
`accountIds` | Array&lt;string&gt;
`taskId` | string
`accountId` | string

## Example

```typescript
import type { BulkDeleteTasksRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "taskIds": null,
  "accountIds": null,
  "taskId": null,
  "accountId": null,
} satisfies BulkDeleteTasksRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkDeleteTasksRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


