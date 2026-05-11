
# CreateContactRequest


## Properties

Name | Type
------------ | -------------
`first_name` | string
`last_name` | string
`email` | string
`phone` | string
`company` | string
`title` | string
`notes` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CreateContactRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "first_name": null,
  "last_name": null,
  "email": null,
  "phone": null,
  "company": null,
  "title": null,
  "notes": null,
  "metadata": null,
} satisfies CreateContactRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateContactRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


