
# TaskListEnvelope

Fan-out response for `GET /v1/tasks`.

## Properties

Name | Type
------------ | -------------
`items` | [Array&lt;Task&gt;](Task.md)
`accounts` | [Array&lt;AccountStatus&gt;](AccountStatus.md)

## Example

```typescript
import type { TaskListEnvelope } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "items": null,
  "accounts": null,
} satisfies TaskListEnvelope

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TaskListEnvelope
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


