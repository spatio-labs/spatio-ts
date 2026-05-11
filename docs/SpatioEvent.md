
# SpatioEvent

A calendar event. Calendar uses snake_case JSON keys (different from Notes/Sheets/Slides/Tasks/Mail which use camelCase) — the surface predates the cross-platform convention. 

## Properties

Name | Type
------------ | -------------
`id` | string
`title` | string
`description` | string
`start_time` | Date
`end_time` | Date
`all_day` | boolean
`location` | string
`location_details` | { [key: string]: string; }
`organizer` | string
`attendees` | [Array&lt;Attendee&gt;](Attendee.md)
`recurrence_rule` | string
`recurrence_id` | string
`original_start` | Date
`status` | string
`visibility` | string
`busy` | boolean
`reminders` | [Array&lt;Reminder&gt;](Reminder.md)
`travel_time_minutes` | number
`categories` | Array&lt;string&gt;
`color` | string
`user_id` | string
`account_id` | string
`provider` | string
`provider_id` | string
`provider_data` | { [key: string]: any; }
`created_at` | Date
`updated_at` | Date
`deleted_at` | Date
`synced_at` | Date
`conference_data` | [ConferenceData](ConferenceData.md)
`attachments` | [Array&lt;Attachment&gt;](Attachment.md)
`url` | string
`etag` | string
`sequence` | number
`custom_data` | { [key: string]: string; }

## Example

```typescript
import type { SpatioEvent } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "title": null,
  "description": null,
  "start_time": null,
  "end_time": null,
  "all_day": null,
  "location": null,
  "location_details": null,
  "organizer": null,
  "attendees": null,
  "recurrence_rule": null,
  "recurrence_id": null,
  "original_start": null,
  "status": null,
  "visibility": null,
  "busy": null,
  "reminders": null,
  "travel_time_minutes": null,
  "categories": null,
  "color": null,
  "user_id": null,
  "account_id": null,
  "provider": null,
  "provider_id": null,
  "provider_data": null,
  "created_at": null,
  "updated_at": null,
  "deleted_at": null,
  "synced_at": null,
  "conference_data": null,
  "attachments": null,
  "url": null,
  "etag": null,
  "sequence": null,
  "custom_data": null,
} satisfies SpatioEvent

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SpatioEvent
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


