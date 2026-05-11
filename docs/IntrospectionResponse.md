
# IntrospectionResponse


## Properties

Name | Type
------------ | -------------
`active` | boolean
`token_type` | string
`client_id` | string
`user_id` | string
`workspace_id` | string
`scope` | string
`exp` | number

## Example

```typescript
import type { IntrospectionResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "active": null,
  "token_type": null,
  "client_id": null,
  "user_id": null,
  "workspace_id": null,
  "scope": null,
  "exp": null,
} satisfies IntrospectionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IntrospectionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


