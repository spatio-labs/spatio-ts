
# NoteListEnvelope

Standard fan-out response for `GET /v1/notes`. Items aggregate notes across every connected account that contributed to the call; each contributing account contributes one `accounts[]` entry — including failed accounts, so the client can render which providers contributed and which errored without the call itself failing. 

## Properties

Name | Type
------------ | -------------
`items` | [Array&lt;Note&gt;](Note.md)
`accounts` | [Array&lt;AccountStatus&gt;](AccountStatus.md)

## Example

```typescript
import type { NoteListEnvelope } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "items": null,
  "accounts": null,
} satisfies NoteListEnvelope

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as NoteListEnvelope
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


