# InboxApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getInboxCounts**](InboxApi.md#getinboxcounts) | **GET** /v1/inbox/counts | Per-bucket unread counts. |
| [**listInbox**](InboxApi.md#listinbox) | **GET** /v1/inbox | Unified inbox feed across mail, channel mentions, DMs, system notifications. |
| [**markInboxItemRead**](InboxApi.md#markinboxitemread) | **PATCH** /v1/inbox/{id}/read | Mark a single inbox item as read. |
| [**workspaceGetInboxCounts**](InboxApi.md#workspacegetinboxcounts) | **GET** /v1/organizations/{org}/workspaces/{workspace}/inbox/counts |  |
| [**workspaceListInbox**](InboxApi.md#workspacelistinbox) | **GET** /v1/organizations/{org}/workspaces/{workspace}/inbox |  |
| [**workspaceMarkInboxItemRead**](InboxApi.md#workspacemarkinboxitemread) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/inbox/{id}/read |  |



## getInboxCounts

> InboxCounts getInboxCounts()

Per-bucket unread counts.

### Example

```ts
import {
  Configuration,
  InboxApi,
} from '@spatio/sdk-ts';
import type { GetInboxCountsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboxApi(config);

  try {
    const data = await api.getInboxCounts();
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

[**InboxCounts**](InboxCounts.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Counts. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listInbox

> InboxListResponse listInbox(category, unreadOnly, limit)

Unified inbox feed across mail, channel mentions, DMs, system notifications.

### Example

```ts
import {
  Configuration,
  InboxApi,
} from '@spatio/sdk-ts';
import type { ListInboxRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboxApi(config);

  const body = {
    // string (optional)
    category: category_example,
    // boolean (optional)
    unreadOnly: true,
    // number (optional)
    limit: 56,
  } satisfies ListInboxRequest;

  try {
    const data = await api.listInbox(body);
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
| **category** | `string` |  | [Optional] [Defaults to `undefined`] |
| **unreadOnly** | `boolean` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**InboxListResponse**](InboxListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Inbox items + counts envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## markInboxItemRead

> markInboxItemRead(id)

Mark a single inbox item as read.

### Example

```ts
import {
  Configuration,
  InboxApi,
} from '@spatio/sdk-ts';
import type { MarkInboxItemReadRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboxApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies MarkInboxItemReadRequest;

  try {
    const data = await api.markInboxItemRead(body);
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
| **204** | Marked read. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Item not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetInboxCounts

> { [key: string]: any; } workspaceGetInboxCounts(org, workspace)



### Example

```ts
import {
  Configuration,
  InboxApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetInboxCountsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboxApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceGetInboxCountsRequest;

  try {
    const data = await api.workspaceGetInboxCounts(body);
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
| **200** | Counts |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListInbox

> { [key: string]: any; } workspaceListInbox(org, workspace)



### Example

```ts
import {
  Configuration,
  InboxApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListInboxRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboxApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListInboxRequest;

  try {
    const data = await api.workspaceListInbox(body);
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
| **200** | Inbox |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceMarkInboxItemRead

> workspaceMarkInboxItemRead(org, workspace, id)



### Example

```ts
import {
  Configuration,
  InboxApi,
} from '@spatio/sdk-ts';
import type { WorkspaceMarkInboxItemReadRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboxApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceMarkInboxItemReadRequest;

  try {
    const data = await api.workspaceMarkInboxItemRead(body);
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
| **204** | Marked |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

