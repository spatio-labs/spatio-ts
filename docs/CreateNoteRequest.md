
# CreateNoteRequest


## Properties

Name | Type
------------ | -------------
`title` | string
`content` | string
`icon` | string
`coverImage` | string
`parentId` | string
`properties` | { [key: string]: any; }
`accountId` | string
`provider` | string

## Example

```typescript
import type { CreateNoteRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "title": null,
  "content": null,
  "icon": null,
  "coverImage": null,
  "parentId": null,
  "properties": null,
  "accountId": null,
  "provider": null,
} satisfies CreateNoteRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateNoteRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


