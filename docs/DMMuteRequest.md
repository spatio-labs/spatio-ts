
# DMMuteRequest

Mute either until a specific time (`untilSeconds`, Unix epoch) or forever (`forever: true`). At least one must be set. 

## Properties

Name | Type
------------ | -------------
`untilSeconds` | number
`forever` | boolean
`accountId` | string

## Example

```typescript
import type { DMMuteRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "untilSeconds": null,
  "forever": null,
  "accountId": null,
} satisfies DMMuteRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as DMMuteRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


