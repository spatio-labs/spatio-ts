
# Contact

Snake-case wire format (legacy).

## Properties

Name | Type
------------ | -------------
`id` | string
`user_id` | string
`organization_id` | string
`first_name` | string
`last_name` | string
`email` | string
`phone` | string
`company` | string
`title` | string
`notes` | string
`scope` | string
`provider` | string
`metadata` | { [key: string]: any; }
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { Contact } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "user_id": null,
  "organization_id": null,
  "first_name": null,
  "last_name": null,
  "email": null,
  "phone": null,
  "company": null,
  "title": null,
  "notes": null,
  "scope": null,
  "provider": null,
  "metadata": null,
  "created_at": null,
  "updated_at": null,
} satisfies Contact

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Contact
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


