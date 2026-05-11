
# UpdateSlideRequest

Partial update — every field optional.

## Properties

Name | Type
------------ | -------------
`title` | string
`notes` | string
`layout` | string
`backgroundColor` | string
`backgroundImageUrl` | string
`textColor` | string
`transition` | string
`position` | number

## Example

```typescript
import type { UpdateSlideRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "title": null,
  "notes": null,
  "layout": null,
  "backgroundColor": null,
  "backgroundImageUrl": null,
  "textColor": null,
  "transition": null,
  "position": null,
} satisfies UpdateSlideRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateSlideRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


