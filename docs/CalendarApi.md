# CalendarApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCalendarEvent**](CalendarApi.md#createcalendarevent) | **POST** /v1/calendar/events | Create a calendar event. |
| [**deleteCalendarEvent**](CalendarApi.md#deletecalendarevent) | **DELETE** /v1/calendar/events/{id} | Delete an event. |
| [**getCalendarCapabilities**](CalendarApi.md#getcalendarcapabilities) | **GET** /v1/calendar/capabilities | Per-account capability flags. |
| [**getCalendarEvent**](CalendarApi.md#getcalendarevent) | **GET** /v1/calendar/events/{id} | Fetch one event. |
| [**listCalendarEvents**](CalendarApi.md#listcalendarevents) | **GET** /v1/calendar/events | List calendar events across connected accounts. |
| [**listCalendarProviders**](CalendarApi.md#listcalendarproviders) | **GET** /v1/calendar/providers | List supported calendar providers. |
| [**syncCalendar**](CalendarApi.md#synccalendar) | **POST** /v1/calendar/sync | Trigger a sync across connected calendar accounts. |
| [**updateCalendarEvent**](CalendarApi.md#updatecalendarevent) | **PATCH** /v1/calendar/events/{id} | Update an event (sparse). |
| [**workspaceCreateCalendarEvent**](CalendarApi.md#workspacecreatecalendarevent) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calendar/events | Workspace-scoped create-event (RBAC-protected). |
| [**workspaceDeleteCalendarEvent**](CalendarApi.md#workspacedeletecalendarevent) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/calendar/events/{id} |  |
| [**workspaceGetCalendarEvent**](CalendarApi.md#workspacegetcalendarevent) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calendar/events/{id} |  |
| [**workspaceListCalendarEvents**](CalendarApi.md#workspacelistcalendarevents) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calendar/events | Workspace-scoped list-events (RBAC-protected). |
| [**workspaceListCalendarProviders**](CalendarApi.md#workspacelistcalendarproviders) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calendar/providers | Workspace-scoped calendar providers. |
| [**workspaceUpdateCalendarEvent**](CalendarApi.md#workspaceupdatecalendarevent) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/calendar/events/{id} |  |



## createCalendarEvent

> CreateCalendarEvent201Response createCalendarEvent(createEventRequest, xWorkspaceID)

Create a calendar event.

Single-account create. &#x60;account_id&#x60; is required (no auto-resolve for write operations). Reminder array is mirrored into native tasks under the hood; conference data is auto-attached when &#x60;conference_type&#x60; is supplied. 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { CreateCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // CreateEventRequest
    createEventRequest: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateCalendarEventRequest;

  try {
    const data = await api.createCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **createEventRequest** | [CreateEventRequest](CreateEventRequest.md) |  | |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**CreateCalendarEvent201Response**](CreateCalendarEvent201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Operation envelope. &#x60;data&#x60; is the created &#x60;Event&#x60;.  |  -  |
| **400** | Invalid body or missing &#x60;account_id&#x60;. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider or capability failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteCalendarEvent

> CalendarOperationResult deleteCalendarEvent(id, accountId, xWorkspaceID)

Delete an event.

Hard delete (no soft-delete / trash). Cascades to any reminder tasks the platform created from this event. 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string | Event id.
    id: id_example,
    // string | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses `accountId`). Required for single-event operations. 
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteCalendarEventRequest;

  try {
    const data = await api.deleteCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | Event id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses &#x60;accountId&#x60;). Required for single-event operations.  | [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**CalendarOperationResult**](CalendarOperationResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Operation envelope. &#x60;metadata&#x60; carries &#x60;deleted_event_id&#x60; and &#x60;deleted_at&#x60;.  |  -  |
| **400** | Missing id or account_id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Event not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getCalendarCapabilities

> CalendarCapabilitiesResponse getCalendarCapabilities(accountId)

Per-account capability flags.

Returns the capabilities the provider declares for the given connected account. The renderer uses these to enable/disable form fields (recurrence picker, attendee inputs, etc.). 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { GetCalendarCapabilitiesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses `accountId`). Required for single-event operations. 
    accountId: accountId_example,
  } satisfies GetCalendarCapabilitiesRequest;

  try {
    const data = await api.getCalendarCapabilities(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **accountId** | `string` | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses &#x60;accountId&#x60;). Required for single-event operations.  | [Defaults to `undefined`] |

### Return type

[**CalendarCapabilitiesResponse**](CalendarCapabilitiesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Capabilities envelope. |  -  |
| **400** | Missing account_id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Account not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getCalendarEvent

> SpatioEvent getCalendarEvent(id, accountId, xWorkspaceID)

Fetch one event.

Requires &#x60;?account_id&#x3D;&#x60; to identify the source account. Response is the bare &#x60;Event&#x60; (not wrapped in CalendarOperationResult — distinct from the list/create/update shapes). 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { GetCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string | Event id.
    id: id_example,
    // string | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses `accountId`). Required for single-event operations. 
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetCalendarEventRequest;

  try {
    const data = await api.getCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | Event id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses &#x60;accountId&#x60;). Required for single-event operations.  | [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SpatioEvent**](SpatioEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The event. |  -  |
| **400** | Missing id or account_id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Event not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCalendarEvents

> ListCalendarEvents200Response listCalendarEvents(accountIds, providers, xWorkspaceID, timeMin, timeMax, limit)

List calendar events across connected accounts.

Fan-out list. Returns events across every connected calendar provider unless filtered by &#x60;account_ids[]&#x60; or &#x60;providers[]&#x60;. Supports the cross-platform repeated-or-comma-separated filter syntax (&#x60;?account_ids&#x3D;a&amp;account_ids&#x3D;b&#x60; or &#x60;?account_ids&#x3D;a,b&#x60;).  Time bounds (&#x60;timeMin&#x60; / &#x60;timeMax&#x60;) accept both RFC3339 and RFC3339Nano. The handler also accepts the snake_case &#x60;time_min&#x60; / &#x60;time_max&#x60; for direct curl callers; the spec models the camelCase form because that\&#39;s what the renderer and SDKs use. 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { ListCalendarEventsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // Array<string> | Repeatable. Restrict to specific connected accounts. (optional)
    accountIds: ...,
    // Array<string> | Repeatable. Restrict to provider ids (`google-calendar`, etc.). (optional)
    providers: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // Date | Inclusive lower-bound time. RFC3339 or RFC3339Nano. (optional)
    timeMin: 2013-10-20T19:20:30+01:00,
    // Date | Inclusive upper-bound time. (optional)
    timeMax: 2013-10-20T19:20:30+01:00,
    // number | Max events to return per page (default 50). (optional)
    limit: 56,
  } satisfies ListCalendarEventsRequest;

  try {
    const data = await api.listCalendarEvents(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **accountIds** | `Array<string>` | Repeatable. Restrict to specific connected accounts. | [Optional] |
| **providers** | `Array<string>` | Repeatable. Restrict to provider ids (&#x60;google-calendar&#x60;, etc.). | [Optional] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **timeMin** | `Date` | Inclusive lower-bound time. RFC3339 or RFC3339Nano. | [Optional] [Defaults to `undefined`] |
| **timeMax** | `Date` | Inclusive upper-bound time. | [Optional] [Defaults to `undefined`] |
| **limit** | `number` | Max events to return per page (default 50). | [Optional] [Defaults to `50`] |

### Return type

[**ListCalendarEvents200Response**](ListCalendarEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Operation envelope. &#x60;data&#x60; is &#x60;ListEventsData&#x60;. Per-account fetch failures appear in &#x60;errors&#x60; rather than failing the whole call.  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Resolver or fan-out failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCalendarProviders

> CalendarProvidersInfo listCalendarProviders()

List supported calendar providers.

Static list of provider ids the Calendar platform can connect to. Returned regardless of which providers the caller has actually authorized. 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { ListCalendarProvidersRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  try {
    const data = await api.listCalendarProviders();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**CalendarProvidersInfo**](CalendarProvidersInfo.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Provider info. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## syncCalendar

> CalendarSyncResponse syncCalendar(wait)

Trigger a sync across connected calendar accounts.

Enqueues sync jobs (one per connected calendar account) and returns immediately with the job ids. Pass &#x60;?wait&#x3D;true&#x60; to block until all jobs complete (10-second polling budget); the response is then &#x60;200&#x60; with &#x60;waited: true&#x60; and a &#x60;timed_out&#x60; flag if any job didn\&#39;t finish in time. 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { SyncCalendarRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // boolean | Block until all sync jobs finish (10s timeout). (optional)
    wait: true,
  } satisfies SyncCalendarRequest;

  try {
    const data = await api.syncCalendar(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **wait** | `boolean` | Block until all sync jobs finish (10s timeout). | [Optional] [Defaults to `false`] |

### Return type

[**CalendarSyncResponse**](CalendarSyncResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Synchronous completion (only when &#x60;?wait&#x3D;true&#x60;). |  -  |
| **202** | Sync jobs enqueued; check the worker for completion. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **503** | Sync queue not configured. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateCalendarEvent

> CreateCalendarEvent201Response updateCalendarEvent(id, updateEventRequest, xWorkspaceID, accountId)

Update an event (sparse).

Partial update. &#x60;account_id&#x60; may be supplied in the body (preferred) or as &#x60;?account_id&#x3D;&#x60; query param — the renderer\&#39;s update path puts it in the URL while create puts it in the body. &#x60;updates&#x60; is a free-form map; the platform\&#39;s capability gate rejects fields the provider doesn\&#39;t support. 

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string | Event id.
    id: id_example,
    // UpdateEventRequest
    updateEventRequest: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // string | Optional account-id filter (snake_case). (optional)
    accountId: accountId_example,
  } satisfies UpdateCalendarEventRequest;

  try {
    const data = await api.updateCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | Event id. | [Defaults to `undefined`] |
| **updateEventRequest** | [UpdateEventRequest](UpdateEventRequest.md) |  | |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **accountId** | `string` | Optional account-id filter (snake_case). | [Optional] [Defaults to `undefined`] |

### Return type

[**CreateCalendarEvent201Response**](CreateCalendarEvent201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Operation envelope. &#x60;data&#x60; is the updated &#x60;Event&#x60;.  |  -  |
| **400** | Invalid body, missing id, or missing account_id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Event not found. |  -  |
| **500** | Provider or capability failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateCalendarEvent

> { [key: string]: any; } workspaceCreateCalendarEvent(org, workspace, requestBody)

Workspace-scoped create-event (RBAC-protected).

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceCreateCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateCalendarEventRequest;

  try {
    const data = await api.workspaceCreateCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **org** | `string` |  | [Defaults to `undefined`] |
| **workspace** | `string` |  | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` |  | |

### Return type

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceDeleteCalendarEvent

> workspaceDeleteCalendarEvent(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceDeleteCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceDeleteCalendarEventRequest;

  try {
    const data = await api.workspaceDeleteCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **org** | `string` |  | [Defaults to `undefined`] |
| **workspace** | `string` |  | [Defaults to `undefined`] |
| **id** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetCalendarEvent

> { [key: string]: any; } workspaceGetCalendarEvent(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetCalendarEventRequest;

  try {
    const data = await api.workspaceGetCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **org** | `string` |  | [Defaults to `undefined`] |
| **workspace** | `string` |  | [Defaults to `undefined`] |
| **id** | `string` |  | [Defaults to `undefined`] |

### Return type

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Event |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListCalendarEvents

> { [key: string]: any; } workspaceListCalendarEvents(org, workspace)

Workspace-scoped list-events (RBAC-protected).

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListCalendarEventsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListCalendarEventsRequest;

  try {
    const data = await api.workspaceListCalendarEvents(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **org** | `string` |  | [Defaults to `undefined`] |
| **workspace** | `string` |  | [Defaults to `undefined`] |

### Return type

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Events |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListCalendarProviders

> { [key: string]: any; } workspaceListCalendarProviders(org, workspace)

Workspace-scoped calendar providers.

### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListCalendarProvidersRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListCalendarProvidersRequest;

  try {
    const data = await api.workspaceListCalendarProviders(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **org** | `string` |  | [Defaults to `undefined`] |
| **workspace** | `string` |  | [Defaults to `undefined`] |

### Return type

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Providers |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUpdateCalendarEvent

> { [key: string]: any; } workspaceUpdateCalendarEvent(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  CalendarApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceUpdateCalendarEventRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CalendarApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateCalendarEventRequest;

  try {
    const data = await api.workspaceUpdateCalendarEvent(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **org** | `string` |  | [Defaults to `undefined`] |
| **workspace** | `string` |  | [Defaults to `undefined`] |
| **id** | `string` |  | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` |  | |

### Return type

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

