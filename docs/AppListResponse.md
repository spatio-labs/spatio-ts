
# AppListResponse


## Properties

Name | Type
------------ | -------------
`apps` | [Array&lt;App&gt;](App.md)
`total` | number

## Example

```typescript
import type { AppListResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "apps": null,
  "total": null,
} satisfies AppListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AppListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


