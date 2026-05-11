
# AgentSessionContext

Identity bundle returned to the agent at SessionStart. One round-trip provides user + current org/workspace + connected accounts so the agent doesn\'t fish on its first turn. 

## Properties

Name | Type
------------ | -------------
`user` | { [key: string]: any; }
`currentOrganization` | { [key: string]: any; }
`currentWorkspace` | { [key: string]: any; }
`connectedAccounts` | Array&lt;{ [key: string]: any; }&gt;

## Example

```typescript
import type { AgentSessionContext } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "user": null,
  "currentOrganization": null,
  "currentWorkspace": null,
  "connectedAccounts": null,
} satisfies AgentSessionContext

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentSessionContext
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


