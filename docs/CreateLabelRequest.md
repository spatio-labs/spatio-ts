
# CreateLabelRequest


## Properties

Name | Type
------------ | -------------
`accountId` | string
`name` | string
`messageListVisibility` | string
`labelListVisibility` | string
`color` | [LabelColor](LabelColor.md)

## Example

```typescript
import type { CreateLabelRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "name": null,
  "messageListVisibility": null,
  "labelListVisibility": null,
  "color": null,
} satisfies CreateLabelRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateLabelRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


