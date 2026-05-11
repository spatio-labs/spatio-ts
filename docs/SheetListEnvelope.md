
# SheetListEnvelope

Fan-out response for `GET /v1/sheets`. `items` aggregates sheets across every connected account; `accounts` carries one row per contributing connection — including failures. 

## Properties

Name | Type
------------ | -------------
`items` | [Array&lt;Sheet&gt;](Sheet.md)
`accounts` | [Array&lt;AccountStatus&gt;](AccountStatus.md)

## Example

```typescript
import type { SheetListEnvelope } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "items": null,
  "accounts": null,
} satisfies SheetListEnvelope

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SheetListEnvelope
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


