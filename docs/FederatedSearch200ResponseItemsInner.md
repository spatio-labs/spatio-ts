
# FederatedSearch200ResponseItemsInner


## Properties

Name | Type
------------ | -------------
`id` | string
`entity_type` | string
`platform` | string
`provider_id` | string
`title` | string
`description` | string
`snippet` | string
`author` | string
`created_at` | Date
`updated_at` | Date
`score` | number

## Example

```typescript
import type { FederatedSearch200ResponseItemsInner } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "entity_type": null,
  "platform": null,
  "provider_id": null,
  "title": null,
  "description": null,
  "snippet": null,
  "author": null,
  "created_at": null,
  "updated_at": null,
  "score": null,
} satisfies FederatedSearch200ResponseItemsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as FederatedSearch200ResponseItemsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


