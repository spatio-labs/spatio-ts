
# SpatioCall


## Properties

Name | Type
------------ | -------------
`id` | string
`title` | string
`status` | string
`hostUserId` | string
`workspaceId` | string
`roomId` | string
`participants` | Array&lt;{ [key: string]: any; }&gt;
`metadata` | { [key: string]: any; }
`startedAt` | Date
`endedAt` | Date
`createdAt` | Date

## Example

```typescript
import type { SpatioCall } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "title": null,
  "status": null,
  "hostUserId": null,
  "workspaceId": null,
  "roomId": null,
  "participants": null,
  "metadata": null,
  "startedAt": null,
  "endedAt": null,
  "createdAt": null,
} satisfies SpatioCall

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SpatioCall
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


