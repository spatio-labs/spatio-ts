
# Slide


## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`presentationId` | string
`title` | string
`notes` | string
`layout` | string
`backgroundColor` | string
`backgroundImageUrl` | string
`textColor` | string
`transition` | string
`position` | number
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { Slide } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "presentationId": null,
  "title": null,
  "notes": null,
  "layout": null,
  "backgroundColor": null,
  "backgroundImageUrl": null,
  "textColor": null,
  "transition": null,
  "position": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies Slide

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Slide
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


