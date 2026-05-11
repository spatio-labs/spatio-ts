
# ActionDescriptor

Action manifest entry surfaced by the agent platform. The `inputType`/`outputType` references point at internal Go types; treat them as opaque labels. 

## Properties

Name | Type
------------ | -------------
`id` | string
`canonical_id` | string
`name` | string
`description` | string
`category` | string
`inputType` | string
`outputType` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { ActionDescriptor } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "canonical_id": null,
  "name": null,
  "description": null,
  "category": null,
  "inputType": null,
  "outputType": null,
  "metadata": null,
} satisfies ActionDescriptor

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ActionDescriptor
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


