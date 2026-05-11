
# ConsumeAgentTaskResponse

Atomic check+increment. Returns the updated counter on success; returns 402 on `trial_expired` and 429 on `daily_limit_exceeded` (the body in error cases is the `ApiError` envelope). 

## Properties

Name | Type
------------ | -------------
`allowed` | boolean
`task_count` | number
`daily_limit` | number
`trial_ends_at` | Date
`paid` | boolean

## Example

```typescript
import type { ConsumeAgentTaskResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "allowed": null,
  "task_count": null,
  "daily_limit": null,
  "trial_ends_at": null,
  "paid": null,
} satisfies ConsumeAgentTaskResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ConsumeAgentTaskResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


