
# Note

A markdown note. Notes belong to exactly one connected account (`accountId` + `provider`). The native provider stores notes in the Spatio database; external providers (Notion, Google Keep, etc.) store them upstream and round-trip through Spatio. 

## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`ownerUserId` | string
`title` | string
`content` | string
`icon` | string
`coverImage` | string
`parentId` | string
`properties` | { [key: string]: any; }
`archived` | boolean
`createdAt` | Date
`updatedAt` | Date
`lastEditedBy` | string

## Example

```typescript
import type { Note } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "ownerUserId": null,
  "title": null,
  "content": null,
  "icon": null,
  "coverImage": null,
  "parentId": null,
  "properties": null,
  "archived": null,
  "createdAt": null,
  "updatedAt": null,
  "lastEditedBy": null,
} satisfies Note

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Note
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


