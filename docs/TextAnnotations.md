
# TextAnnotations

Inline formatting flags for a `RichTextObject`.

## Properties

Name | Type
------------ | -------------
`bold` | boolean
`italic` | boolean
`strikethrough` | boolean
`underline` | boolean
`code` | boolean
`color` | string

## Example

```typescript
import type { TextAnnotations } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "bold": null,
  "italic": null,
  "strikethrough": null,
  "underline": null,
  "code": null,
  "color": null,
} satisfies TextAnnotations

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TextAnnotations
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


