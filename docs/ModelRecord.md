
# ModelRecord


## Properties

Name | Type
------------ | -------------
`id` | string
`organization_id` | string
`record_type_id` | string
`name` | string
`attributes` | { [key: string]: any; }
`metadata` | { [key: string]: any; }
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { ModelRecord } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "organization_id": null,
  "record_type_id": null,
  "name": null,
  "attributes": null,
  "metadata": null,
  "created_at": null,
  "updated_at": null,
} satisfies ModelRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ModelRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


