
# UpdateEmailRequest

Mark messages read/unread, star, or add/remove labels. All fields optional — only present fields are touched. 

## Properties

Name | Type
------------ | -------------
`accountId` | string
`isRead` | boolean
`isStarred` | boolean
`addLabels` | Array&lt;string&gt;
`removeLabels` | Array&lt;string&gt;

## Example

```typescript
import type { UpdateEmailRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "isRead": null,
  "isStarred": null,
  "addLabels": null,
  "removeLabels": null,
} satisfies UpdateEmailRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateEmailRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


