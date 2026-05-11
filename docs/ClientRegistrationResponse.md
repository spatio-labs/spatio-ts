
# ClientRegistrationResponse


## Properties

Name | Type
------------ | -------------
`client_id` | string
`client_secret` | string
`client_name` | string
`redirect_uris` | Array&lt;string&gt;
`grant_types` | Array&lt;string&gt;
`response_types` | Array&lt;string&gt;
`scope` | string
`token_endpoint_auth_method` | string
`registration_access_token` | string
`registration_client_uri` | string
`client_id_issued_at` | number

## Example

```typescript
import type { ClientRegistrationResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "client_id": null,
  "client_secret": null,
  "client_name": null,
  "redirect_uris": null,
  "grant_types": null,
  "response_types": null,
  "scope": null,
  "token_endpoint_auth_method": null,
  "registration_access_token": null,
  "registration_client_uri": null,
  "client_id_issued_at": null,
} satisfies ClientRegistrationResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ClientRegistrationResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


