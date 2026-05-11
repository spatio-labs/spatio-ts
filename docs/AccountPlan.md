
# AccountPlan

Subscription summary. `tier` is the canonical billing tier (uppercased: `FREE`, `PRO`, `MAX`, `ENTERPRISE`); `display_name` is the lowercase user-facing label. 

## Properties

Name | Type
------------ | -------------
`tier` | string
`display_name` | string
`subscription_status` | string
`trial_ends_at` | Date

## Example

```typescript
import type { AccountPlan } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "tier": null,
  "display_name": null,
  "subscription_status": null,
  "trial_ends_at": null,
} satisfies AccountPlan

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountPlan
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


