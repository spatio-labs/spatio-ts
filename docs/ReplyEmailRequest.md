
# ReplyEmailRequest

Reply to a specific email. `to/cc/bcc` are optional — the platform falls back to the original sender / recipients when omitted. 

## Properties

Name | Type
------------ | -------------
`accountId` | string
`to` | Array&lt;string&gt;
`cc` | Array&lt;string&gt;
`bcc` | Array&lt;string&gt;
`body` | string
`html` | boolean
`attachments` | [Array&lt;AttachmentInput&gt;](AttachmentInput.md)

## Example

```typescript
import type { ReplyEmailRequest } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "to": null,
  "cc": null,
  "bcc": null,
  "body": null,
  "html": null,
  "attachments": null,
} satisfies ReplyEmailRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ReplyEmailRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


