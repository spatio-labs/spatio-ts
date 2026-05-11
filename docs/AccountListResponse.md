
# AccountListResponse

`GET /v1/accounts` returns `{accounts_by_platform, total_accounts}` on production today. Schema kept open until the consumers migrate to a flat `accounts` array. 

## Properties

Name | Type
------------ | -------------
`accounts_by_platform` | { [key: string]: any; }
`total_accounts` | number
`accounts` | Array&lt;{ [key: string]: any; }&gt;

## Example

```typescript
import type { AccountListResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "accounts_by_platform": null,
  "total_accounts": null,
  "accounts": null,
} satisfies AccountListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


