
# BulkMarkReadRequest

Bulk shorthand for setting read state on many messages at once. `messageIds` accepts an array; the production handler also accepts a bare string for renderer-compat but the spec models the array shape only. `read` defaults to `true` when omitted. 

## Properties

Name | Type
------------ | -------------
`accountId` | string
`messageIds` | Array&lt;string&gt;
`read` | boolean

## Example

```typescript
import type { BulkMarkReadRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "messageIds": null,
  "read": null,
} satisfies BulkMarkReadRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BulkMarkReadRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


