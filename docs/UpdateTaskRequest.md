
# UpdateTaskRequest

Partial update — every field is optional. `dueDate` and `parentTaskId` are nullable: send `null` to clear, omit to leave untouched, send a value to set. 

## Properties

Name | Type
------------ | -------------
`title` | string
`description` | string
`status` | string
`dueDate` | Date
`priority` | string
`labels` | Array&lt;string&gt;
`tags` | Array&lt;string&gt;
`assigneeId` | string
`parentTaskId` | string

## Example

```typescript
import type { UpdateTaskRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "title": null,
  "description": null,
  "status": null,
  "dueDate": null,
  "priority": null,
  "labels": null,
  "tags": null,
  "assigneeId": null,
  "parentTaskId": null,
} satisfies UpdateTaskRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateTaskRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


