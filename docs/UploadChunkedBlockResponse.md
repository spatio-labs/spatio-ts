
# UploadChunkedBlockResponse


## Properties

Name | Type
------------ | -------------
`blockHash` | string
`uploaded` | boolean
`blocksRemaining` | number
`progress` | number

## Example

```typescript
import type { UploadChunkedBlockResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "blockHash": null,
  "uploaded": null,
  "blocksRemaining": null,
  "progress": null,
} satisfies UploadChunkedBlockResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UploadChunkedBlockResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


