
# ExportPDFR2Response

Response shape when the export was uploaded to R2 (`?storage=r2`). The streaming case (`?storage=stream`, default) returns a binary `application/pdf` body and is not modeled as a JSON schema. 

## Properties

Name | Type
------------ | -------------
`storage` | string
`url` | string
`expiresAt` | Date
`size` | number

## Example

```typescript
import type { ExportPDFR2Response } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "storage": null,
  "url": null,
  "expiresAt": null,
  "size": null,
} satisfies ExportPDFR2Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExportPDFR2Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


