
# DMForwardRequest

Forward to either a DM (`toDmId`) or a channel (`toChannelId`); exactly one required.

## Properties

Name | Type
------------ | -------------
`toDmId` | string
`toChannelId` | string
`accountId` | string

## Example

```typescript
import type { DMForwardRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "toDmId": null,
  "toChannelId": null,
  "accountId": null,
} satisfies DMForwardRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as DMForwardRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


