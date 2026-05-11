
# PreconfiguredAgent

Curated featured agents — read-only, surfaced by the renderer\'s \"preconfigured\" picker. Not full Agent records; minimal display metadata only. 

## Properties

Name | Type
------------ | -------------
`agentId` | string
`name` | string
`tagline` | string
`description` | string
`icon` | string
`hasAllTools` | boolean
`toolCount` | number

## Example

```typescript
import type { PreconfiguredAgent } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "agentId": null,
  "name": null,
  "tagline": null,
  "description": null,
  "icon": null,
  "hasAllTools": null,
  "toolCount": null,
} satisfies PreconfiguredAgent

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PreconfiguredAgent
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


