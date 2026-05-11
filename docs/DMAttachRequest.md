
# DMAttachRequest


## Properties

Name | Type
------------ | -------------
`kind` | string
`url` | string
`filename` | string
`sizeBytes` | number
`mimeType` | string
`thumbnailUrl` | string
`width` | number
`height` | number
`accountId` | string

## Example

```typescript
import type { DMAttachRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "kind": null,
  "url": null,
  "filename": null,
  "sizeBytes": null,
  "mimeType": null,
  "thumbnailUrl": null,
  "width": null,
  "height": null,
  "accountId": null,
} satisfies DMAttachRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as DMAttachRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


