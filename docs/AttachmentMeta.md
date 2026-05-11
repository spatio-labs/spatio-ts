
# AttachmentMeta

Attachment metadata; binary fetched via the attachment endpoint.

## Properties

Name | Type
------------ | -------------
`id` | string
`filename` | string
`contentType` | string
`size` | number

## Example

```typescript
import type { AttachmentMeta } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "filename": null,
  "contentType": null,
  "size": null,
} satisfies AttachmentMeta

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AttachmentMeta
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


