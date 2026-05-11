
# MeetingRoom


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`workspaceId` | string
`createdAt` | Date

## Example

```typescript
import type { MeetingRoom } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "workspaceId": null,
  "createdAt": null,
} satisfies MeetingRoom

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MeetingRoom
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


