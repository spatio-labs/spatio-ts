
# ListMessagesResponse


## Properties

Name | Type
------------ | -------------
`messages` | [Array&lt;ChatMessage&gt;](ChatMessage.md)
`hasMore` | boolean
`nextCursor` | string
`provider` | string

## Example

```typescript
import type { ListMessagesResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "messages": null,
  "hasMore": null,
  "nextCursor": null,
  "provider": null,
} satisfies ListMessagesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListMessagesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


