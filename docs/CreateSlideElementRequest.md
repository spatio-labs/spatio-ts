
# CreateSlideElementRequest


## Properties

Name | Type
------------ | -------------
`elementType` | string
`content` | { [key: string]: any; }
`x` | number
`y` | number
`width` | number
`height` | number
`rotation` | number
`zIndex` | number

## Example

```typescript
import type { CreateSlideElementRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "elementType": null,
  "content": null,
  "x": null,
  "y": null,
  "width": null,
  "height": null,
  "rotation": null,
  "zIndex": null,
} satisfies CreateSlideElementRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateSlideElementRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


