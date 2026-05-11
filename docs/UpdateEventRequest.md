
# UpdateEventRequest

Sparse update. `updates` is a free-form map of fields to change; only keys present are applied. The server-side capability gate rejects fields that the underlying provider doesn\'t support. 

## Properties

Name | Type
------------ | -------------
`account_id` | string
`updates` | { [key: string]: any; }
`send_updates` | string

## Example

```typescript
import type { UpdateEventRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "account_id": null,
  "updates": null,
  "send_updates": null,
} satisfies UpdateEventRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateEventRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


