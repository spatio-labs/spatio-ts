
# CalendarAccountError


## Properties

Name | Type
------------ | -------------
`account_id` | string
`account_name` | string
`error_code` | string
`error_message` | string

## Example

```typescript
import type { CalendarAccountError } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "account_id": null,
  "account_name": null,
  "error_code": null,
  "error_message": null,
} satisfies CalendarAccountError

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CalendarAccountError
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


