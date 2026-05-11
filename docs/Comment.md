
# Comment

Threaded comment on a note. Top-level comments have `parentCommentId: null`; replies set it to the parent comment\'s id. `blockId` anchors the comment to a specific block; comments without a `blockId` are note-level (\"general\") comments. 

## Properties

Name | Type
------------ | -------------
`id` | string
`noteId` | string
`parentCommentId` | string
`blockId` | string
`body` | string
`createdAt` | Date
`updatedAt` | Date
`author` | [CommentAuthor](CommentAuthor.md)

## Example

```typescript
import type { Comment } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "noteId": null,
  "parentCommentId": null,
  "blockId": null,
  "body": null,
  "createdAt": null,
  "updatedAt": null,
  "author": null,
} satisfies Comment

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Comment
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


