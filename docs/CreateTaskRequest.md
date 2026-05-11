
# CreateTaskRequest


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
`type` | string
`sourcePlatform` | string
`sourceId` | string
`accountId` | string
`provider` | string

## Example

```typescript
import type { CreateTaskRequest } from '@spatio/sdk-ts'

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
  "type": null,
  "sourcePlatform": null,
  "sourceId": null,
  "accountId": null,
  "provider": null,
} satisfies CreateTaskRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateTaskRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


