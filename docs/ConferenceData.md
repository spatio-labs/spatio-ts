
# ConferenceData

Video/phone conference details. `type` is canonical (`spatio`, `meet`, `zoom`, `teams`); other provider-specific values are accepted as opaque strings. The Spatio invite email pipeline only fires for native events or events with `type: spatio`. 

## Properties

Name | Type
------------ | -------------
`type` | string
`uri` | string
`meeting_id` | string
`passcode` | string
`access_code` | string
`dial_in` | Array&lt;string&gt;

## Example

```typescript
import type { ConferenceData } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "type": null,
  "uri": null,
  "meeting_id": null,
  "passcode": null,
  "access_code": null,
  "dial_in": null,
} satisfies ConferenceData

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ConferenceData
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


