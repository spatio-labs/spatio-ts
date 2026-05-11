
# SpatioThread


## Properties

Name | Type
------------ | -------------
`id` | string
`messages` | [Array&lt;Email&gt;](Email.md)
`snippet` | string
`labels` | Array&lt;string&gt;

## Example

```typescript
import type { SpatioThread } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "messages": null,
  "snippet": null,
  "labels": null,
} satisfies SpatioThread

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SpatioThread
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


