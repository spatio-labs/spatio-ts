
# CalendarSyncResponse

Returned by `POST /v1/calendar/sync`. Status code is `202` by default (sync jobs queued); `200` when called with `?wait=true` and all jobs finish within the 10-second polling budget. 

## Properties

Name | Type
------------ | -------------
`enqueued` | number
`jobs` | Array&lt;string&gt;
`waited` | boolean
`timed_out` | boolean
`errors` | Array&lt;{ [key: string]: any; }&gt;

## Example

```typescript
import type { CalendarSyncResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "enqueued": null,
  "jobs": null,
  "waited": null,
  "timed_out": null,
  "errors": null,
} satisfies CalendarSyncResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CalendarSyncResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


