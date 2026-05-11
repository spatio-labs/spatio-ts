
# ContactListResponse


## Properties

Name | Type
------------ | -------------
`contacts` | [Array&lt;Contact&gt;](Contact.md)
`total_results` | number
`updated_at` | Date

## Example

```typescript
import type { ContactListResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "contacts": null,
  "total_results": null,
  "updated_at": null,
} satisfies ContactListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ContactListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


