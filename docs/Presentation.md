
# Presentation

A slide deck. Presentations belong to one connected account (`accountId` + `provider`). Native deck storage lives in Spatio\'s DB; external providers (Google Slides, etc.) round-trip. 

## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`ownerUserId` | string
`title` | string
`description` | string
`theme` | string
`thumbnailUrl` | string
`createdAt` | Date
`updatedAt` | Date
`lastViewedAt` | Date

## Example

```typescript
import type { Presentation } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "ownerUserId": null,
  "title": null,
  "description": null,
  "theme": null,
  "thumbnailUrl": null,
  "createdAt": null,
  "updatedAt": null,
  "lastViewedAt": null,
} satisfies Presentation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Presentation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


