
# CreateBlockRequest


## Properties

Name | Type
------------ | -------------
`type` | [BlockType](BlockType.md)
`content` | [BlockContent](BlockContent.md)
`parentId` | string
`position` | number
`properties` | { [key: string]: any; }

## Example

```typescript
import type { CreateBlockRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "type": null,
  "content": null,
  "parentId": null,
  "position": null,
  "properties": null,
} satisfies CreateBlockRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateBlockRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


