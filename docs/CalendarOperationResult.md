
# CalendarOperationResult

Generic platform-operation envelope used by Calendar list/create/ update/delete responses. `data` is operation-specific:   - listEvents: `ListEventsData`   - createEvent / updateEvent: `Event`   - deleteEvent: empty / metadata-only 

## Properties

Name | Type
------------ | -------------
`success` | boolean
`data` | any
`errors` | [Array&lt;CalendarAccountError&gt;](CalendarAccountError.md)
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CalendarOperationResult } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "success": null,
  "data": null,
  "errors": null,
  "metadata": null,
} satisfies CalendarOperationResult

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CalendarOperationResult
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


