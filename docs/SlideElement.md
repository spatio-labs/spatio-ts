
# SlideElement

One canvas object on a slide — text box, shape, image, etc. `content` is renderer-specific JSON (e.g. fabric.js properties: text, fill, fontSize, src). Identified by a stable `id` so MCP / agent operations stay idempotent across retries. 

## Properties

Name | Type
------------ | -------------
`id` | string
`slideId` | string
`elementType` | string
`content` | { [key: string]: any; }
`x` | number
`y` | number
`width` | number
`height` | number
`rotation` | number
`zIndex` | number
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { SlideElement } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "slideId": null,
  "elementType": null,
  "content": null,
  "x": null,
  "y": null,
  "width": null,
  "height": null,
  "rotation": null,
  "zIndex": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies SlideElement

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SlideElement
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


