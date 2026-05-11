
# CreateNote400Response


## Properties

Name | Type
------------ | -------------
`error` | string
`code` | string
`accounts` | [Array&lt;AccountChoice&gt;](AccountChoice.md)

## Example

```typescript
import type { CreateNote400Response } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "error": user not authenticated,
  "code": ambiguous_account,
  "accounts": null,
} satisfies CreateNote400Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateNote400Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


