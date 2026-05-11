
# BulkDeleteEmailsRequest

Soft-deletes by default (moves to provider trash). Set `permanent: true` to hard-delete. 

## Properties

Name | Type
------------ | -------------
`accountId` | string
`messageIds` | Array&lt;string&gt;
`permanent` | boolean

## Example

```typescript
import type { BulkDeleteEmailsRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "messageIds": null,
  "permanent": null,
} satisfies BulkDeleteEmailsRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkDeleteEmailsRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


