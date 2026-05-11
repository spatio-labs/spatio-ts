
# RichTextObject


## Properties

Name | Type
------------ | -------------
`type` | string
`text` | string
`annotations` | [TextAnnotations](TextAnnotations.md)
`href` | string

## Example

```typescript
import type { RichTextObject } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "type": null,
  "text": null,
  "annotations": null,
  "href": null,
} satisfies RichTextObject

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RichTextObject
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


