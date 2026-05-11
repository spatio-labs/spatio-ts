
# ListEventsData

Shape of `data` when returned by `listEvents`. Wrapped inside a CalendarOperationResult — clients should access this as `result.data` after checking `result.success`. 

## Properties

Name | Type
------------ | -------------
`events` | [Array&lt;SpatioEvent&gt;](SpatioEvent.md)
`next_page_token` | string
`total_results` | number
`updated_at` | Date

## Example

```typescript
import type { ListEventsData } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "events": null,
  "next_page_token": null,
  "total_results": null,
  "updated_at": null,
} satisfies ListEventsData

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListEventsData
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


