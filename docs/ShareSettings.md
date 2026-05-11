
# ShareSettings

Public share configuration for a note. Owner-only mutation; unauthenticated readers consume `GET /public/notes/{token}` instead. 

## Properties

Name | Type
------------ | -------------
`isPublic` | boolean
`hasPassword` | boolean
`shareToken` | string
`shareUrl` | string
`passwordSetAt` | Date

## Example

```typescript
import type { ShareSettings } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "isPublic": null,
  "hasPassword": null,
  "shareToken": null,
  "shareUrl": null,
  "passwordSetAt": null,
} satisfies ShareSettings

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ShareSettings
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


