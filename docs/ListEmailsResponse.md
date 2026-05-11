
# ListEmailsResponse

List of emails across the selected accounts. `provider` is set on single-account calls; on fan-out it carries the value from the first contributing account (legacy behavior — clients should rely on the per-row `provider` field instead). 

## Properties

Name | Type
------------ | -------------
`emails` | [Array&lt;Email&gt;](Email.md)
`total` | number
`nextPageToken` | string
`provider` | string

## Example

```typescript
import type { ListEmailsResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "emails": null,
  "total": null,
  "nextPageToken": null,
  "provider": null,
} satisfies ListEmailsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListEmailsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


