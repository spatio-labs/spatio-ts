
# Cell

A single cell. `value` is the JSON-serializable cell contents; interpretation is provider-specific. 

## Properties

Name | Type
------------ | -------------
`row` | number
`column` | string
`value` | any

## Example

```typescript
import type { Cell } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "row": null,
  "column": null,
  "value": null,
} satisfies Cell

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Cell
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


