
# InitChunkedUploadResponse


## Properties

Name | Type
------------ | -------------
`sessionId` | string
`blocksToUpload` | Array&lt;string&gt;
`blocksAlreadyExist` | Array&lt;string&gt;
`deduplicationPct` | number
`estimatedUploadSize` | number

## Example

```typescript
import type { InitChunkedUploadResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "sessionId": null,
  "blocksToUpload": null,
  "blocksAlreadyExist": null,
  "deduplicationPct": null,
  "estimatedUploadSize": null,
} satisfies InitChunkedUploadResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InitChunkedUploadResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


