
# ContactCategory


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`color` | string
`description` | string
`organization_id` | string

## Example

```typescript
import type { ContactCategory } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "color": null,
  "description": null,
  "organization_id": null,
} satisfies ContactCategory

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ContactCategory
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


