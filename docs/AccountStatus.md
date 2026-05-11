
# AccountStatus

Outcome of one connected account\'s contribution to a fan-out call. Every connection that participated appears in `Envelope.accounts` exactly once, regardless of whether it succeeded, errored, or returned zero items. 

## Properties

Name | Type
------------ | -------------
`provider` | string
`accountId` | string
`accountName` | string
`status` | string
`error` | [AccountError](AccountError.md)
`nextPageToken` | string

## Example

```typescript
import type { AccountStatus } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "accountId": null,
  "accountName": null,
  "status": null,
  "error": null,
  "nextPageToken": null,
} satisfies AccountStatus

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountStatus
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


