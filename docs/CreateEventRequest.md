
# CreateEventRequest


## Properties

Name | Type
------------ | -------------
`account_id` | string
`calendar_id` | string
`event` | [SpatioEvent](SpatioEvent.md)
`send_updates` | string
`conference_type` | string

## Example

```typescript
import type { CreateEventRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "account_id": null,
  "calendar_id": null,
  "event": null,
  "send_updates": null,
  "conference_type": null,
} satisfies CreateEventRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateEventRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


