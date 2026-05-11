
# ClientRegistrationRequest


## Properties

Name | Type
------------ | -------------
`client_name` | string
`redirect_uris` | Array&lt;string&gt;
`grant_types` | Array&lt;string&gt;
`response_types` | Array&lt;string&gt;
`scope` | string
`token_endpoint_auth_method` | string
`client_uri` | string
`logo_uri` | string
`policy_uri` | string
`tos_uri` | string

## Example

```typescript
import type { ClientRegistrationRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "client_name": null,
  "redirect_uris": null,
  "grant_types": null,
  "response_types": null,
  "scope": null,
  "token_endpoint_auth_method": null,
  "client_uri": null,
  "logo_uri": null,
  "policy_uri": null,
  "tos_uri": null,
} satisfies ClientRegistrationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ClientRegistrationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


