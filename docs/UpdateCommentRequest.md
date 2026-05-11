
# UpdateCommentRequest

Either `body` (preferred) or `content` is required. 

## Properties

Name | Type
------------ | -------------
`body` | string
`content` | string

## Example

```typescript
import type { UpdateCommentRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "body": null,
  "content": null,
} satisfies UpdateCommentRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateCommentRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


