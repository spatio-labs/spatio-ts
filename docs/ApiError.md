
# ApiError

Standard error envelope returned by 4xx and 5xx responses across the SpatioAPI. Some endpoints attach extra machine-readable fields (`code`, `accounts`, `requiresPassword`, etc.) — those are documented on the individual operation. 

## Properties

Name | Type
------------ | -------------
`error` | string
`code` | string

## Example

```typescript
import type { ApiError } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "error": user not authenticated,
  "code": ambiguous_account,
} satisfies ApiError

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ApiError
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


