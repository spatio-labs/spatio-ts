
# AccountUsage

Today\'s usage counters. Snapshot reflects the in-memory rollup; counts reset at UTC midnight.

## Properties

Name | Type
------------ | -------------
`date` | string
`api_calls` | number
`email_sends` | number
`notes_count` | number
`sheets_count` | number
`slides_count` | number
`files_count` | number
`tasks_count` | number

## Example

```typescript
import type { AccountUsage } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "date": null,
  "api_calls": null,
  "email_sends": null,
  "notes_count": null,
  "sheets_count": null,
  "slides_count": null,
  "files_count": null,
  "tasks_count": null,
} satisfies AccountUsage

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountUsage
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


