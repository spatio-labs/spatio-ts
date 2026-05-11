
# RecordListResponse


## Properties

Name | Type
------------ | -------------
`records` | [Array&lt;ModelRecord&gt;](ModelRecord.md)
`total_results` | number
`updated_at` | Date

## Example

```typescript
import type { RecordListResponse } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "records": null,
  "total_results": null,
  "updated_at": null,
} satisfies RecordListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RecordListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


