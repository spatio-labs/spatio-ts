
# InboxItem

A unified-feed item. Source-aware — `category` indicates which upstream platform (mail, dm, channel, mention, system) produced it; `id` is the inbox-item id (not the underlying message id). 

## Properties

Name | Type
------------ | -------------
`id` | string
`category` | string
`title` | string
`snippet` | string
`source` | string
`sourceId` | string
`accountId` | string
`isRead` | boolean
`isMention` | boolean
`timestamp` | Date
`metadata` | { [key: string]: any; }

## Example

```typescript
import type { InboxItem } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "category": null,
  "title": null,
  "snippet": null,
  "source": null,
  "sourceId": null,
  "accountId": null,
  "isRead": null,
  "isMention": null,
  "timestamp": null,
  "metadata": null,
} satisfies InboxItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboxItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


