
# BulkUpdateTasksRequest

Apply the same `updates` payload to every id. Same parallel AccountIDs convention as bulk delete. 

## Properties

Name | Type
------------ | -------------
`taskIds` | Array&lt;string&gt;
`accountIds` | Array&lt;string&gt;
`accountId` | string
`updates` | [UpdateTaskRequest](UpdateTaskRequest.md)

## Example

```typescript
import type { BulkUpdateTasksRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "taskIds": null,
  "accountIds": null,
  "accountId": null,
  "updates": null,
} satisfies BulkUpdateTasksRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkUpdateTasksRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


