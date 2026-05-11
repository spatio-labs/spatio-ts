
# JWK

A single JSON Web Key (RFC 7517 §4) — RSA public key.

## Properties

Name | Type
------------ | -------------
`kty` | string
`use` | string
`alg` | string
`kid` | string
`n` | string
`e` | string

## Example

```typescript
import type { JWK } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "kty": RSA,
  "use": sig,
  "alg": RS256,
  "kid": null,
  "n": null,
  "e": null,
} satisfies JWK

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as JWK
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


