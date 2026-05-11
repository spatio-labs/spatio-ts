
# CalendarCapabilitiesResponse


## Properties

Name | Type
------------ | -------------
`account_id` | string
`provider_id` | string
`capabilities` | { [key: string]: any; }

## Example

```typescript
import type { CalendarCapabilitiesResponse } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "account_id": null,
  "provider_id": null,
  "capabilities": null,
} satisfies CalendarCapabilitiesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CalendarCapabilitiesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


