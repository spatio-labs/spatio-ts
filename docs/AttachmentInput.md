
# AttachmentInput

Inline attachment payload for `send`, `reply`, and draft requests. `data` is the raw bytes base64-encoded by the JSON encoder. 

## Properties

Name | Type
------------ | -------------
`filename` | string
`contentType` | string
`data` | string
`size` | number

## Example

```typescript
import type { AttachmentInput } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "filename": null,
  "contentType": null,
  "data": null,
  "size": null,
} satisfies AttachmentInput

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AttachmentInput
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


