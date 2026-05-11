
# Email

A single email message. The `provider`/`accountId` provenance fields tell clients which connected mail account this row came from (Gmail, Outlook, etc.) so multi-account list responses can be merged sensibly client-side. 

## Properties

Name | Type
------------ | -------------
`id` | string
`threadId` | string
`provider` | string
`accountId` | string
`subject` | string
`from` | string
`to` | Array&lt;string&gt;
`cc` | Array&lt;string&gt;
`bcc` | Array&lt;string&gt;
`body` | string
`html` | boolean
`date` | Date
`labels` | Array&lt;string&gt;
`isRead` | boolean
`isStarred` | boolean
`attachments` | [Array&lt;AttachmentMeta&gt;](AttachmentMeta.md)
`snippet` | string
`messageId` | string
`inReplyTo` | string
`references` | Array&lt;string&gt;

## Example

```typescript
import type { Email } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "threadId": null,
  "provider": null,
  "accountId": null,
  "subject": null,
  "from": null,
  "to": null,
  "cc": null,
  "bcc": null,
  "body": null,
  "html": null,
  "date": null,
  "labels": null,
  "isRead": null,
  "isStarred": null,
  "attachments": null,
  "snippet": null,
  "messageId": null,
  "inReplyTo": null,
  "references": null,
} satisfies Email

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Email
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


