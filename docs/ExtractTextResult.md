
# ExtractTextResult

Extracted text + structural metadata from a PDF (or other extraction-supported file type). `pages` is provider-shaped — treat as an opaque per-page object array. Endpoint returns `422` with `code: extraction_unsupported` when the underlying file isn\'t extractable. 

## Properties

Name | Type
------------ | -------------
`text` | string
`pageCount` | number
`pages` | Array&lt;{ [key: string]: any; }&gt;
`truncated` | boolean

## Example

```typescript
import type { ExtractTextResult } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "text": null,
  "pageCount": null,
  "pages": null,
  "truncated": null,
} satisfies ExtractTextResult

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExtractTextResult
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


