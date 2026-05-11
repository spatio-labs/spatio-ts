
# ChannelMembershipRequest

Body for join/leave operations.

## Properties

Name | Type
------------ | -------------
`accountId` | string

## Example

```typescript
import type { ChannelMembershipRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
} satisfies ChannelMembershipRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ChannelMembershipRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


