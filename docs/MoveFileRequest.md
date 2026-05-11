
# MoveFileRequest

Move a single file to a target folder. Pass `folderId: null` to move to the account root. Bulk moves use `POST /v1/files/move`. 

## Properties

Name | Type
------------ | -------------
`folderId` | string

## Example

```typescript
import type { MoveFileRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "folderId": null,
} satisfies MoveFileRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MoveFileRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


