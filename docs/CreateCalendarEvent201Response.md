
# CreateCalendarEvent201Response


## Properties

Name | Type
------------ | -------------
`success` | boolean
`data` | [SpatioEvent](SpatioEvent.md)
`errors` | [Array&lt;CalendarAccountError&gt;](CalendarAccountError.md)
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CreateCalendarEvent201Response } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "data": null,
  "errors": null,
  "metadata": null,
} satisfies CreateCalendarEvent201Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateCalendarEvent201Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


