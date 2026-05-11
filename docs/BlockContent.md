
# BlockContent

Type-specific payload for a block. Fields populated depend on `Block.type`. All fields are optional at the schema level; the runtime enforces the per-type contract.  Note: this object uses snake_case keys to match the JSON the Go `providers.BlockContent` struct emits and accepts. Other parts of the SpatioAPI use camelCase; blocks are the exception because the block model is shared with external Notion-like providers whose canonical wire format is snake_case. 

## Properties

Name | Type
------------ | -------------
`rich_text` | [Array&lt;RichTextObject&gt;](RichTextObject.md)
`language` | string
`checked` | boolean
`icon` | string
`color` | string
`url` | string
`caption` | string
`alt_text` | string
`embed_url` | string
`cells` | Array&lt;Array&lt;RichTextObject&gt;&gt;
`expression` | string

## Example

```typescript
import type { BlockContent } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "rich_text": null,
  "language": null,
  "checked": null,
  "icon": null,
  "color": null,
  "url": null,
  "caption": null,
  "alt_text": null,
  "embed_url": null,
  "cells": null,
  "expression": null,
} satisfies BlockContent

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BlockContent
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


