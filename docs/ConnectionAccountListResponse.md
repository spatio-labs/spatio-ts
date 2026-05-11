
# ConnectionAccountListResponse

`GET /v1/connections/user` returns `{connections, user_id}` (the per-provider connected-account list). Schema kept open pending a normalize-to-`accounts` migration. 

## Properties

Name | Type
------------ | -------------
`connections` | Array&lt;{ [key: string]: any; }&gt;
`user_id` | string
`accounts` | Array&lt;{ [key: string]: any; }&gt;

## Example

```typescript
import type { ConnectionAccountListResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "connections": null,
  "user_id": null,
  "accounts": null,
} satisfies ConnectionAccountListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ConnectionAccountListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


