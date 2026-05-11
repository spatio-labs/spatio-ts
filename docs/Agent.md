
# Agent

Stored agent configuration (system prompt + tool selection). User-defined agents and preconfigured agents share this shape. 

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`systemPrompt` | string
`tools` | Array&lt;string&gt;
`icon` | string
`color` | string
`isDefault` | boolean
`isPreconfigured` | boolean
`createdAt` | Date
`updatedAt` | Date
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { Agent } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "systemPrompt": null,
  "tools": null,
  "icon": null,
  "color": null,
  "isDefault": null,
  "isPreconfigured": null,
  "createdAt": null,
  "updatedAt": null,
  "metadata": null,
} satisfies Agent

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Agent
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


