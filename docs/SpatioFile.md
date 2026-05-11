
# SpatioFile

A user file. Files belong to one connected file provider account (`accountId` + `provider`); native storage uses Spatio\'s block-store, external providers (Google Drive, Dropbox, etc.) round-trip through Spatio.  Schema name is `SpatioFile` (not `File`) to avoid the `java.io.File` collision that breaks the Kotlin SDK generator when the schema is named `File`. 

## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`name` | string
`size` | number
`mimeType` | string
`folderId` | string
`storageType` | string
`downloadUrl` | string
`metadata` | { [key: string]: any; }
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { SpatioFile } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "name": null,
  "size": null,
  "mimeType": null,
  "folderId": null,
  "storageType": null,
  "downloadUrl": null,
  "metadata": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies SpatioFile

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SpatioFile
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


