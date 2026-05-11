
# AccountTierDetails

Per-tier capability + quota envelope. Numeric quotas use 0/-1 idioms; treat large negatives as \"unlimited.\"

## Properties

Name | Type
------------ | -------------
`tier` | string
`daily_api_calls` | number
`max_connected_accounts` | number
`max_email_sends_per_day` | number
`max_notes` | number
`max_sheets` | number
`max_slides` | number
`max_files` | number
`max_tasks` | number
`max_team_members` | number
`max_workspaces` | number
`storage_gb` | number
`has_automations` | boolean
`has_advanced_automations` | boolean
`has_full_api_access` | boolean

## Example

```typescript
import type { AccountTierDetails } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "tier": null,
  "daily_api_calls": null,
  "max_connected_accounts": null,
  "max_email_sends_per_day": null,
  "max_notes": null,
  "max_sheets": null,
  "max_slides": null,
  "max_files": null,
  "max_tasks": null,
  "max_team_members": null,
  "max_workspaces": null,
  "storage_gb": null,
  "has_automations": null,
  "has_advanced_automations": null,
  "has_full_api_access": null,
} satisfies AccountTierDetails

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountTierDetails
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


