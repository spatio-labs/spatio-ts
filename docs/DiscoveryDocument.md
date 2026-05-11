
# DiscoveryDocument

OAuth 2.1 (RFC 8414) + OpenID Connect Discovery 1.0 metadata. Same payload returned from both well-known paths. 

## Properties

Name | Type
------------ | -------------
`issuer` | string
`authorization_endpoint` | string
`token_endpoint` | string
`registration_endpoint` | string
`introspection_endpoint` | string
`revocation_endpoint` | string
`userinfo_endpoint` | string
`jwks_uri` | string
`response_types_supported` | Array&lt;string&gt;
`grant_types_supported` | Array&lt;string&gt;
`token_endpoint_auth_methods_supported` | Array&lt;string&gt;
`code_challenge_methods_supported` | Array&lt;string&gt;
`scopes_supported` | Array&lt;string&gt;
`subject_types_supported` | Array&lt;string&gt;
`id_token_signing_alg_values_supported` | Array&lt;string&gt;
`prompt_values_supported` | Array&lt;string&gt;
`claims_supported` | Array&lt;string&gt;
`service_documentation` | string

## Example

```typescript
import type { DiscoveryDocument } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "issuer": https://api.spatio.app,
  "authorization_endpoint": https://api.spatio.app/oauth2/authorize,
  "token_endpoint": https://api.spatio.app/oauth2/token,
  "registration_endpoint": null,
  "introspection_endpoint": null,
  "revocation_endpoint": null,
  "userinfo_endpoint": null,
  "jwks_uri": https://api.spatio.app/.well-known/jwks.json,
  "response_types_supported": null,
  "grant_types_supported": null,
  "token_endpoint_auth_methods_supported": null,
  "code_challenge_methods_supported": ["S256"],
  "scopes_supported": null,
  "subject_types_supported": ["public"],
  "id_token_signing_alg_values_supported": ["RS256"],
  "prompt_values_supported": ["none","login","consent"],
  "claims_supported": null,
  "service_documentation": null,
} satisfies DiscoveryDocument

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as DiscoveryDocument
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


