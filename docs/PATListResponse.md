
# PATListResponse


## Properties

Name | Type
------------ | -------------
`tokens` | [Array&lt;PersonalAccessToken&gt;](PersonalAccessToken.md)
`availableScopes` | Array&lt;string&gt;

## Example

```typescript
import type { PATListResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "tokens": null,
  "availableScopes": null,
} satisfies PATListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PATListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


