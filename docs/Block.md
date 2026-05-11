
# Block


## Properties

Name | Type
------------ | -------------
`id` | string
`noteId` | string
`parentId` | string
`type` | [BlockType](BlockType.md)
`content` | [BlockContent](BlockContent.md)
`properties` | { [key: string]: any; }
`position` | number
`hasChildren` | boolean
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { Block } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "noteId": null,
  "parentId": null,
  "type": null,
  "content": null,
  "properties": null,
  "position": null,
  "hasChildren": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies Block

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Block
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


