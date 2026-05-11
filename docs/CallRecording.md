
# CallRecording


## Properties

Name | Type
------------ | -------------
`id` | string
`callId` | string
`status` | string
`startedAt` | Date
`endedAt` | Date
`url` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CallRecording } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "callId": null,
  "status": null,
  "startedAt": null,
  "endedAt": null,
  "url": null,
  "metadata": null,
} satisfies CallRecording

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CallRecording
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


