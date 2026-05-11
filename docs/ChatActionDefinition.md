
# ChatActionDefinition

One entry in `GET /actions`. Action ids are dotted (e.g. `direct-messages.send`, `channels.list`); the `executeAction` endpoint accepts the id with a free-form `params` object. 

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`platform` | string
`category` | string
`inputType` | string
`outputType` | string
`scopes` | Array&lt;string&gt;
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { ChatActionDefinition } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "platform": null,
  "category": null,
  "inputType": null,
  "outputType": null,
  "scopes": null,
  "metadata": null,
} satisfies ChatActionDefinition

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ChatActionDefinition
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


