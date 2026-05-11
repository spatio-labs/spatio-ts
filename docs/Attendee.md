
# Attendee


## Properties

Name | Type
------------ | -------------
`email` | string
`name` | string
`status` | [AttendeeStatus](AttendeeStatus.md)
`role` | [AttendeeRole](AttendeeRole.md)
`optional` | boolean
`comment` | string
`additional_guests` | number

## Example

```typescript
import type { Attendee } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "email": null,
  "name": null,
  "status": null,
  "role": null,
  "optional": null,
  "comment": null,
  "additional_guests": null,
} satisfies Attendee

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Attendee
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


