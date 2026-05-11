
# OrganizationDetailLegacy

Single-organization GET response. **PascalCase keys** — inconsistent with the rest of the API (anonymous-struct json-marshal in handler with no field tags). Documented as-is; a future cleanup pass will move this to camelCase via a versioned migration. 

## Properties

Name | Type
------------ | -------------
`ID` | string
`Name` | string
`Slug` | string
`Description` | string
`LogoURL` | string
`Settings` | string
`SubscriptionTier` | string
`DeploymentType` | string
`SubscriptionStatus` | string
`CreatedAt` | Date
`UpdatedAt` | Date

## Example

```typescript
import type { OrganizationDetailLegacy } from '@spatio/sdk-ts'

// TODO: Update the object below with actual values
const example = {
  "ID": null,
  "Name": null,
  "Slug": null,
  "Description": null,
  "LogoURL": null,
  "Settings": null,
  "SubscriptionTier": null,
  "DeploymentType": null,
  "SubscriptionStatus": null,
  "CreatedAt": null,
  "UpdatedAt": null,
} satisfies OrganizationDetailLegacy

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OrganizationDetailLegacy
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


