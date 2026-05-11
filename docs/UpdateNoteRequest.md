
# UpdateNoteRequest

Partial update. Every field is optional; only fields present in the body are touched. `null` for `parentId` clears the parent. 

## Properties

Name | Type
------------ | -------------
`title` | string
`content` | string
`icon` | string
`coverImage` | string
`parentId` | string
`properties` | { [key: string]: any; }
`archived` | boolean

## Example

```typescript
import type { UpdateNoteRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "title": null,
  "content": null,
  "icon": null,
  "coverImage": null,
  "parentId": null,
  "properties": null,
  "archived": null,
} satisfies UpdateNoteRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateNoteRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


