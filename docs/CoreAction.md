
# CoreAction

Renderer-curated \"core action\" entry. These are the keyboard + command-palette surfaced actions; superset of the platform-tagged agent actions. Schema kept open since the platform metadata varies by category. 

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`platform` | string
`category` | string
`icon` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { CoreAction } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "platform": null,
  "category": null,
  "icon": null,
  "metadata": null,
} satisfies CoreAction

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CoreAction
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


