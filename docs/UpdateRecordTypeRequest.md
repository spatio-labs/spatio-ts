
# UpdateRecordTypeRequest


## Properties

Name | Type
------------ | -------------
`slug` | string
`name` | string
`name_plural` | string
`icon` | string
`attribute_schema` | Array&lt;{ [key: string]: any; }&gt;

## Example

```typescript
import type { UpdateRecordTypeRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "slug": null,
  "name": null,
  "name_plural": null,
  "icon": null,
  "attribute_schema": null,
} satisfies UpdateRecordTypeRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateRecordTypeRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


