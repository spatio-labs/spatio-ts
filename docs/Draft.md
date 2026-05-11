
# Draft


## Properties

Name | Type
------------ | -------------
`id` | string
`messageId` | string
`threadId` | string
`to` | Array&lt;string&gt;
`cc` | Array&lt;string&gt;
`bcc` | Array&lt;string&gt;
`subject` | string
`body` | string
`html` | boolean
`attachments` | [Array&lt;AttachmentMeta&gt;](AttachmentMeta.md)
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { Draft } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "messageId": null,
  "threadId": null,
  "to": null,
  "cc": null,
  "bcc": null,
  "subject": null,
  "body": null,
  "html": null,
  "attachments": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies Draft

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Draft
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


