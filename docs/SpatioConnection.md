
# SpatioConnection

OAuth/native integration descriptor. Open shape — categories add provider-specific capability flags. Treat unknown fields as additive. 

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`category` | string
`description` | string
`authType` | string
`connected` | boolean
`connectedAccounts` | Array&lt;{ [key: string]: any; }&gt;
`capabilities` | { [key: string]: any; }
`gradientFrom` | string
`gradientTo` | string
`icon` | string

## Example

```typescript
import type { SpatioConnection } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "category": null,
  "description": null,
  "authType": null,
  "connected": null,
  "connectedAccounts": null,
  "capabilities": null,
  "gradientFrom": null,
  "gradientTo": null,
  "icon": null,
} satisfies SpatioConnection

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SpatioConnection
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


