
# TaskCommentList


## Properties

Name | Type
------------ | -------------
`comments` | [Array&lt;TaskComment&gt;](TaskComment.md)
`total` | number

## Example

```typescript
import type { TaskCommentList } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "comments": null,
  "total": null,
} satisfies TaskCommentList

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TaskCommentList
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


