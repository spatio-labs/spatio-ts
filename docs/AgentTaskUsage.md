
# AgentTaskUsage

Free-trial agent-task gate. `allowed` is the only field clients must check before issuing a turn. Paid users get `paid: true, allowed: true` with the count fields null. 

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
import type { AgentTaskUsage } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "allowed": null,
  "task_count": null,
  "daily_limit": null,
  "trial_ends_at": null,
  "paid": null,
} satisfies AgentTaskUsage

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentTaskUsage
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


