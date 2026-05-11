
# BlockType

Discriminator for block types. The structure of `content` varies by type (e.g. `paragraph` carries `richText`; `code` carries `richText` + `language`; `image` carries `url` + `caption` + `altText`). 

## Properties

Name | Type
------------ | -------------

## Example

```typescript
import type { BlockType } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
} satisfies BlockType

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BlockType
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


