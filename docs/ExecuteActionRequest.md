
# ExecuteActionRequest

Generic action-execute payload. Tool-specific shape lives in `params`.

## Properties

Name | Type
------------ | -------------
`actionId` | string
`params` | { [key: string]: any; }
`accountId` | string

## Example

```typescript
import type { ExecuteActionRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "actionId": null,
  "params": null,
  "accountId": null,
} satisfies ExecuteActionRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExecuteActionRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


