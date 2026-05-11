
# Sheet

A spreadsheet. Sheets belong to exactly one connected account (`accountId` + `provider`). The native provider stores sheets in the Spatio database; external providers (Google Sheets, Excel Online, etc.) round-trip through Spatio.  `data` is a free-form bag for provider-specific blobs (cell matrices, formulas, formatting). Clients that walk rows / cells should use the dedicated row + cell endpoints; `data` is only meaningful when round-tripping with an external provider that embeds its native format here. 

## Properties

Name | Type
------------ | -------------
`id` | string
`provider` | string
`accountId` | string
`ownerUserId` | string
`name` | string
`description` | string
`data` | { [key: string]: any; }
`rowCount` | number
`columnCount` | number
`sheetCount` | number
`isPublic` | boolean
`isReadOnly` | boolean
`fileSize` | number
`lastAccessedAt` | Date
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { Sheet } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "provider": null,
  "accountId": null,
  "ownerUserId": null,
  "name": null,
  "description": null,
  "data": null,
  "rowCount": null,
  "columnCount": null,
  "sheetCount": null,
  "isPublic": null,
  "isReadOnly": null,
  "fileSize": null,
  "lastAccessedAt": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies Sheet

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Sheet
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


