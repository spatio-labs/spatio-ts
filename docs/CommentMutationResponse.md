
# CommentMutationResponse

Response for `POST` and `PATCH` on a comment.

## Properties

Name | Type
------------ | -------------
`comment` | [Comment](Comment.md)
`success` | boolean

## Example

```typescript
import type { CommentMutationResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "comment": null,
  "success": null,
} satisfies CommentMutationResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CommentMutationResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


