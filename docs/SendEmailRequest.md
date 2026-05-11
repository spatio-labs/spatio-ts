
# SendEmailRequest


## Properties

Name | Type
------------ | -------------
`accountId` | string
`to` | Array&lt;string&gt;
`cc` | Array&lt;string&gt;
`bcc` | Array&lt;string&gt;
`subject` | string
`body` | string
`html` | boolean
`attachments` | [Array&lt;AttachmentInput&gt;](AttachmentInput.md)
`inReplyTo` | string
`references` | Array&lt;string&gt;

## Example

```typescript
import type { SendEmailRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "accountId": null,
  "to": null,
  "cc": null,
  "bcc": null,
  "subject": null,
  "body": null,
  "html": null,
  "attachments": null,
  "inReplyTo": null,
  "references": null,
} satisfies SendEmailRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SendEmailRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


