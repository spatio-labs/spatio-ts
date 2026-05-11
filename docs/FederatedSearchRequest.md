
# FederatedSearchRequest


## Properties

Name | Type
------------ | -------------
`query` | string
`platforms` | Array&lt;string&gt;
`limit` | number
`page_tokens` | { [key: string]: string; }
`workspace_id` | string
`organization_id` | string
`include_shared` | boolean
`include_archived` | boolean

## Example

```typescript
import type { FederatedSearchRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "query": null,
  "platforms": null,
  "limit": null,
  "page_tokens": null,
  "workspace_id": null,
  "organization_id": null,
  "include_shared": null,
  "include_archived": null,
} satisfies FederatedSearchRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as FederatedSearchRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


