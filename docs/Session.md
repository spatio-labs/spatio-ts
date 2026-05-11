
# Session


## Properties

Name | Type
------------ | -------------
`id` | string
`ipAddress` | string
`userAgent` | string
`deviceType` | string
`browser` | string
`os` | string
`country` | string
`city` | string
`createdAt` | Date
`lastActiveAt` | Date
`isCurrent` | boolean

## Example

```typescript
import type { Session } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "ipAddress": null,
  "userAgent": null,
  "deviceType": null,
  "browser": null,
  "os": null,
  "country": null,
  "city": null,
  "createdAt": null,
  "lastActiveAt": null,
  "isCurrent": null,
} satisfies Session

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Session
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


