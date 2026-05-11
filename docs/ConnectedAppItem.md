
# ConnectedAppItem


## Properties

Name | Type
------------ | -------------
`client_id` | string
`client_name` | string
`logo_uri` | string
`client_uri` | string
`policy_uri` | string
`tos_uri` | string
`scopes` | Array&lt;string&gt;
`scope_labels` | Array&lt;string&gt;
`granted_at` | Date

## Example

```typescript
import type { ConnectedAppItem } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "client_id": null,
  "client_name": null,
  "logo_uri": null,
  "client_uri": null,
  "policy_uri": null,
  "tos_uri": null,
  "scopes": null,
  "scope_labels": null,
  "granted_at": null,
} satisfies ConnectedAppItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ConnectedAppItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


