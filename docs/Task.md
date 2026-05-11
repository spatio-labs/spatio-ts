
# Task

A to-do / reminder / issue. Tasks belong to one connected account (`accountId` + `provider`). Native tasks store in Spatio\'s DB; external providers (Linear, GitHub Issues, Todoist, etc.) round-trip through Spatio. 

## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`ownerUserId` | string
`title` | string
`description` | string
`status` | string
`completed` | boolean
`dueDate` | Date
`priority` | string
`labels` | Array&lt;string&gt;
`tags` | Array&lt;string&gt;
`assigneeId` | string
`createdAt` | Date
`updatedAt` | Date
`completedAt` | Date
`parentTaskId` | string
`metadata` | { [key: string]: any; }
`type` | string
`sourcePlatform` | string
`sourceId` | string

## Example

```typescript
import type { Task } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "ownerUserId": null,
  "title": null,
  "description": null,
  "status": null,
  "completed": null,
  "dueDate": null,
  "priority": null,
  "labels": null,
  "tags": null,
  "assigneeId": null,
  "createdAt": null,
  "updatedAt": null,
  "completedAt": null,
  "parentTaskId": null,
  "metadata": null,
  "type": null,
  "sourcePlatform": null,
  "sourceId": null,
} satisfies Task

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Task
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


