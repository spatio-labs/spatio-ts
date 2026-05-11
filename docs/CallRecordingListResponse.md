
# CallRecordingListResponse


## Properties

Name | Type
------------ | -------------
`recordings` | [Array&lt;CallRecording&gt;](CallRecording.md)

## Example

```typescript
import type { CallRecordingListResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "recordings": null,
} satisfies CallRecordingListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CallRecordingListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


