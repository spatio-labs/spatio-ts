
# UpdateSheetRequest

Partial update — every field is optional.

## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`data` | { [key: string]: any; }
`rowCount` | number
`columnCount` | number
`isPublic` | boolean
`isReadOnly` | boolean

## Example

```typescript
import type { UpdateSheetRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "name": null,
  "description": null,
  "data": null,
  "rowCount": null,
  "columnCount": null,
  "isPublic": null,
  "isReadOnly": null,
} satisfies UpdateSheetRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateSheetRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


