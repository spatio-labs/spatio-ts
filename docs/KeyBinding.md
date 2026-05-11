
# KeyBinding

Merged user-customized key binding.

## Properties

Name | Type
------------ | -------------
`id` | string
`actionId` | string
`displayName` | string
`description` | string
`key` | string
`modifiers` | Array&lt;string&gt;
`category` | string
`scope` | string
`displayOrder` | number
`isCustom` | boolean
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { KeyBinding } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "actionId": null,
  "displayName": null,
  "description": null,
  "key": null,
  "modifiers": null,
  "category": null,
  "scope": null,
  "displayOrder": null,
  "isCustom": null,
  "metadata": null,
} satisfies KeyBinding

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as KeyBinding
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


