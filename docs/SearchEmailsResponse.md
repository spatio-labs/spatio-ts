
# SearchEmailsResponse


## Properties

Name | Type
------------ | -------------
`emails` | [Array&lt;Email&gt;](Email.md)
`total` | number
`nextPageToken` | string
`provider` | string

## Example

```typescript
import type { SearchEmailsResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "emails": null,
  "total": null,
  "nextPageToken": null,
  "provider": null,
} satisfies SearchEmailsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchEmailsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


