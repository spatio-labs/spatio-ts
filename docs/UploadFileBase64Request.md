
# UploadFileBase64Request


## Properties

Name | Type
------------ | -------------
`accountId` | string
`name` | string
`content` | string
`mimeType` | string
`folderId` | string
`workspaceId` | string
`organizationId` | string
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { UploadFileBase64Request } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "name": null,
  "content": null,
  "mimeType": null,
  "folderId": null,
  "workspaceId": null,
  "organizationId": null,
  "metadata": null,
} satisfies UploadFileBase64Request

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UploadFileBase64Request
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


