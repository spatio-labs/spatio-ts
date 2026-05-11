
# Attachment


## Properties

Name | Type
------------ | -------------
`id` | string
`title` | string
`mime_type` | string
`url` | string
`size` | number

## Example

```typescript
import type { Attachment } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "title": null,
  "mime_type": null,
  "url": null,
  "size": null,
} satisfies Attachment

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Attachment
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


