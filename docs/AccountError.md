
# AccountError

Per-account failure attached to `AccountStatus.error` inside a fan-out `Envelope`. `code` is machine-readable and stable across releases for the canonical values (`auth_expired`, `rate_limited`, `provider_5xx`, `timeout`); `unknown` is a fallback and should not be relied on. 

## Properties

Name | Type
------------ | -------------
`code` | string
`message` | string

## Example

```typescript
import type { AccountError } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "code": auth_expired,
  "message": null,
} satisfies AccountError

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountError
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


