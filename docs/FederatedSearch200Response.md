
# FederatedSearch200Response


## Properties

Name | Type
------------ | -------------
`items` | [Array&lt;FederatedSearch200ResponseItemsInner&gt;](FederatedSearch200ResponseItemsInner.md)
`next_page_tokens` | { [key: string]: string; }
`per_platform` | [{ [key: string]: FederatedSearch200ResponsePerPlatformValue; }](FederatedSearch200ResponsePerPlatformValue.md)
`errors` | { [key: string]: string; }
`total_returned` | number
`took` | string

## Example

```typescript
import type { FederatedSearch200Response } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "items": null,
  "next_page_tokens": null,
  "per_platform": null,
  "errors": null,
  "total_returned": null,
  "took": null,
} satisfies FederatedSearch200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as FederatedSearch200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


