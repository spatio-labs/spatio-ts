
# UpdateParticipantStateRequest

Toggle audio/video/screen-share state.

## Properties

Name | Type
------------ | -------------
`audioEnabled` | boolean
`videoEnabled` | boolean
`screenShareEnabled` | boolean

## Example

```typescript
import type { UpdateParticipantStateRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "audioEnabled": null,
  "videoEnabled": null,
  "screenShareEnabled": null,
} satisfies UpdateParticipantStateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateParticipantStateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


