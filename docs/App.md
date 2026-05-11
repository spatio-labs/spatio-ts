
# App

Locally-built prototype app rendered in an Electron <webview>. `projectPath` is the on-disk root; file ops are scoped to it. 

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`projectPath` | string
`icon` | string
`color` | string
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { App } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "projectPath": null,
  "icon": null,
  "color": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies App

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as App
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


