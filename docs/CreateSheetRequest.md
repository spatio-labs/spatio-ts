
# CreateSheetRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`data` | { [key: string]: any; }
`rowCount` | number
`columnCount` | number
`accountId` | string
`provider` | string

## Example

```typescript
import type { CreateSheetRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "name": null,
  "description": null,
  "data": null,
  "rowCount": null,
  "columnCount": null,
  "accountId": null,
  "provider": null,
} satisfies CreateSheetRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateSheetRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


