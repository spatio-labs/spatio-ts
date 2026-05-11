
# UpdateBlockRequest

Partial update — only fields present in the body are touched.

## Properties

Name | Type
------------ | -------------
`content` | [BlockContent](BlockContent.md)
`properties` | { [key: string]: any; }
`archived` | boolean

## Example

```typescript
import type { UpdateBlockRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "content": null,
  "properties": null,
  "archived": null,
} satisfies UpdateBlockRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateBlockRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


