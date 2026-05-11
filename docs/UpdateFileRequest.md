
# UpdateFileRequest

Partial update.

## Properties

Name | Type
------------ | -------------
`name` | string
`folderId` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { UpdateFileRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "name": null,
  "folderId": null,
  "metadata": null,
} satisfies UpdateFileRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateFileRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


