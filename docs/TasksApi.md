# TasksApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**bulkDeleteTasks**](TasksApi.md#bulkdeletetasksoperation) | **POST** /v1/tasks/delete | Delete multiple tasks in one call. |
| [**bulkUpdateTasks**](TasksApi.md#bulkupdatetasksoperation) | **POST** /v1/tasks/bulk-update | Apply the same update to multiple tasks. |
| [**completeTask**](TasksApi.md#completetask) | **POST** /v1/tasks/{id}/complete | Mark a task complete. |
| [**createTask**](TasksApi.md#createtaskoperation) | **POST** /v1/tasks | Create a task. |
| [**createTaskComment**](TasksApi.md#createtaskcomment) | **POST** /v1/tasks/{id}/comments | Create a comment. |
| [**deleteTask**](TasksApi.md#deletetask) | **DELETE** /v1/tasks/{id} | Delete a task. |
| [**deleteTaskComment**](TasksApi.md#deletetaskcomment) | **DELETE** /v1/tasks/{id}/comments/{commentId} | Delete a task comment. |
| [**getTask**](TasksApi.md#gettask) | **GET** /v1/tasks/{id} | Fetch one task. |
| [**listTaskComments**](TasksApi.md#listtaskcomments) | **GET** /v1/tasks/{id}/comments | List comments on a task. |
| [**listTaskProviders**](TasksApi.md#listtaskproviders) | **GET** /v1/tasks/providers | List supported task providers. |
| [**listTasks**](TasksApi.md#listtasks) | **GET** /v1/tasks | List tasks across connected accounts. |
| [**updateTask**](TasksApi.md#updatetaskoperation) | **PATCH** /v1/tasks/{id} | Update a task (partial). |
| [**updateTaskComment**](TasksApi.md#updatetaskcomment) | **PATCH** /v1/tasks/{id}/comments/{commentId} | Edit a task comment. |
| [**workspaceCompleteTask**](TasksApi.md#workspacecompletetask) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id}/complete |  |
| [**workspaceCompleteTaskAlias**](TasksApi.md#workspacecompletetaskalias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/complete/task | Renderer-compat alias for /tasks/{id}/complete. |
| [**workspaceCreateTask**](TasksApi.md#workspacecreatetask) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks |  |
| [**workspaceCreateTaskAlias**](TasksApi.md#workspacecreatetaskalias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/task | Renderer-compat alias for POST /tasks. |
| [**workspaceDeleteTask**](TasksApi.md#workspacedeletetask) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspaceGetTask**](TasksApi.md#workspacegettask) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspaceListTaskProviders**](TasksApi.md#workspacelisttaskproviders) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/providers |  |
| [**workspaceListTasks**](TasksApi.md#workspacelisttasks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks |  |
| [**workspaceListTasksAlias**](TasksApi.md#workspacelisttasksalias) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/tasks | Renderer-compat alias for /tasks. |
| [**workspaceUpdateTask**](TasksApi.md#workspaceupdatetask) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspaceUpdateTaskAlias**](TasksApi.md#workspaceupdatetaskalias) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/tasks/task/{id} | Renderer-compat alias for PATCH /tasks/{id}. |



## bulkDeleteTasks

> BulkDeleteTasksResponse bulkDeleteTasks(bulkDeleteTasksRequest)

Delete multiple tasks in one call.

Replaces the legacy BFF that looped DELETE /v1/tasks/:id. Per-id errors are collected in &#x60;failed&#x60; rather than failing the whole call — partial success is the norm. 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { BulkDeleteTasksOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // BulkDeleteTasksRequest
    bulkDeleteTasksRequest: ...,
  } satisfies BulkDeleteTasksOperationRequest;

  try {
    const data = await api.bulkDeleteTasks(body);
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
| **bulkDeleteTasksRequest** | [BulkDeleteTasksRequest](BulkDeleteTasksRequest.md) |  | |

### Return type

[**BulkDeleteTasksResponse**](BulkDeleteTasksResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Partial-success envelope. |  -  |
| **400** | Body missing or &#x60;taskIds&#x60; empty. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## bulkUpdateTasks

> BulkUpdateTasksResponse bulkUpdateTasks(bulkUpdateTasksRequest)

Apply the same update to multiple tasks.

Same &#x60;updates&#x60; payload applied to every id in &#x60;taskIds&#x60;. As with bulk delete, per-id failures collect in &#x60;failed&#x60;. 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { BulkUpdateTasksOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // BulkUpdateTasksRequest
    bulkUpdateTasksRequest: ...,
  } satisfies BulkUpdateTasksOperationRequest;

  try {
    const data = await api.bulkUpdateTasks(body);
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
| **bulkUpdateTasksRequest** | [BulkUpdateTasksRequest](BulkUpdateTasksRequest.md) |  | |

### Return type

[**BulkUpdateTasksResponse**](BulkUpdateTasksResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Partial-success envelope. |  -  |
| **400** | Body missing or &#x60;taskIds&#x60; empty. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## completeTask

> SuccessFlag completeTask(id, accountId, xWorkspaceID)

Mark a task complete.

Idempotent — completing an already-completed task is a no-op that still returns success. The legacy &#x60;POST /v1/tasks/complete/task&#x60; endpoint accepts the same operation with the task id in the JSON body instead of the URL; that variant is a renderer-compat shim and is not modeled in the spec. 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { CompleteTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CompleteTaskRequest;

  try {
    const data = await api.completeTask(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Task not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createTask

> Task createTask(createTaskRequest, accountId, provider, xWorkspaceID)

Create a task.

Creates a new task under the target account. Target resolution mirrors &#x60;POST /v1/notes&#x60;: body &#x60;accountId&#x60; → &#x60;?accountId&#x3D;&#x60; → body &#x60;provider&#x60; → &#x60;?provider&#x3D;&#x60; → caller\&#39;s single connected account (errors &#x60;ambiguous_account&#x60; if more than one and no selector). 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { CreateTaskOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // CreateTaskRequest
    createTaskRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateTaskOperationRequest;

  try {
    const data = await api.createTask(body);
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
| **createTaskRequest** | [CreateTaskRequest](CreateTaskRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Task**](Task.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Task created. |  -  |
| **400** | Invalid body, ambiguous account (&#x60;code: ambiguous_account&#x60;), or no tasks provider connected (&#x60;code: no_task_provider&#x60;).  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createTaskComment

> TaskCommentMutationResponse createTaskComment(id, taskCommentRequest, accountId, xWorkspaceID)

Create a comment.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { CreateTaskCommentRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // TaskCommentRequest
    taskCommentRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateTaskCommentRequest;

  try {
    const data = await api.createTaskComment(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **taskCommentRequest** | [TaskCommentRequest](TaskCommentRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**TaskCommentMutationResponse**](TaskCommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment created. |  -  |
| **400** | Missing content or task id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteTask

> SuccessFlag deleteTask(id, accountId, xWorkspaceID)

Delete a task.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { DeleteTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteTaskRequest;

  try {
    const data = await api.deleteTask(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Task not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteTaskComment

> SuccessFlag deleteTaskComment(id, commentId, accountId, xWorkspaceID)

Delete a task comment.

Allowed for the comment author and (for native comments) for the task owner. 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { DeleteTaskCommentRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // string | Comment id.
    commentId: commentId_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteTaskCommentRequest;

  try {
    const data = await api.deleteTaskComment(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **commentId** | `string` | Comment id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **400** | Missing comment id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is neither the author nor the task owner. |  -  |
| **404** | Comment not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getTask

> Task getTask(id, accountId, xWorkspaceID)

Fetch one task.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { GetTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetTaskRequest;

  try {
    const data = await api.getTask(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Task**](Task.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The task. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Task not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTaskComments

> TaskCommentList listTaskComments(id, accountId, xWorkspaceID)

List comments on a task.

Returns active comments. When &#x60;?accountId&#x3D;&#x60; targets an external provider that supports comments (e.g. Linear), the provider is queried directly; otherwise the native &#x60;TaskComment&#x60; table is used. 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { ListTaskCommentsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies ListTaskCommentsRequest;

  try {
    const data = await api.listTaskComments(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**TaskCommentList**](TaskCommentList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment list. |  -  |
| **400** | Missing task id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTaskProviders

> TaskProvidersInfo listTaskProviders()

List supported task providers.

Returns the registered task-provider ids and the platform\&#39;s own metadata. Useful for clients that need to render provider-specific UI (icons, capability flags) before committing to a particular &#x60;provider&#x60;. 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { ListTaskProvidersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  try {
    const data = await api.listTaskProviders();
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

[**TaskProvidersInfo**](TaskProvidersInfo.md)

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


## listTasks

> TaskListEnvelope listTasks(accountId, provider, xWorkspaceID, completed, labels, parentTaskId, type, sourcePlatform, sourceId, limit, offset)

List tasks across connected accounts.

Fan-out list. Returns every task visible to the caller across every connected tasks provider. Pass &#x60;?accountId&#x3D;&#x60; or &#x60;?provider&#x3D;&#x60; to scope to a single source. 

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { ListTasksRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // boolean | Include completed tasks. Default `false` (active tasks only).  (optional)
    completed: true,
    // Array<string> | Repeatable. Filter to tasks carrying every label listed. (optional)
    labels: ...,
    // string | Filter to subtasks of this parent. (optional)
    parentTaskId: parentTaskId_example,
    // string | Discriminator filter (`todo`, `reminder`, `issue`).  (optional)
    type: type_example,
    // string | Filter to tasks linked to a given source platform. (optional)
    sourcePlatform: sourcePlatform_example,
    // string | Filter to tasks linked to a specific source artifact id. Pair with `sourcePlatform` for an exact match.  (optional)
    sourceId: sourceId_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
  } satisfies ListTasksRequest;

  try {
    const data = await api.listTasks(body);
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
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **completed** | `boolean` | Include completed tasks. Default &#x60;false&#x60; (active tasks only).  | [Optional] [Defaults to `false`] |
| **labels** | `Array<string>` | Repeatable. Filter to tasks carrying every label listed. | [Optional] |
| **parentTaskId** | `string` | Filter to subtasks of this parent. | [Optional] [Defaults to `undefined`] |
| **type** | `string` | Discriminator filter (&#x60;todo&#x60;, &#x60;reminder&#x60;, &#x60;issue&#x60;).  | [Optional] [Defaults to `undefined`] |
| **sourcePlatform** | `string` | Filter to tasks linked to a given source platform. | [Optional] [Defaults to `undefined`] |
| **sourceId** | `string` | Filter to tasks linked to a specific source artifact id. Pair with &#x60;sourcePlatform&#x60; for an exact match.  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |

### Return type

[**TaskListEnvelope**](TaskListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Fan-out envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Resolver or fan-out failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTask

> Task updateTask(id, updateTaskRequest, accountId, xWorkspaceID)

Update a task (partial).

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { UpdateTaskOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // UpdateTaskRequest
    updateTaskRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateTaskOperationRequest;

  try {
    const data = await api.updateTask(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **updateTaskRequest** | [UpdateTaskRequest](UpdateTaskRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Task**](Task.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated task. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Task not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTaskComment

> TaskCommentMutationResponse updateTaskComment(id, commentId, taskCommentRequest, accountId, xWorkspaceID)

Edit a task comment.

Only the comment author can edit.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { UpdateTaskCommentRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string | Task id.
    id: id_example,
    // string | Comment id.
    commentId: commentId_example,
    // TaskCommentRequest
    taskCommentRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateTaskCommentRequest;

  try {
    const data = await api.updateTaskComment(body);
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
| **id** | `string` | Task id. | [Defaults to `undefined`] |
| **commentId** | `string` | Comment id. | [Defaults to `undefined`] |
| **taskCommentRequest** | [TaskCommentRequest](TaskCommentRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**TaskCommentMutationResponse**](TaskCommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment updated. |  -  |
| **400** | Missing content or comment id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the comment author. |  -  |
| **404** | Comment not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCompleteTask

> { [key: string]: any; } workspaceCompleteTask(org, workspace, id)



### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCompleteTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceCompleteTaskRequest;

  try {
    const data = await api.workspaceCompleteTask(body);
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
| **200** | Completed |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCompleteTaskAlias

> { [key: string]: any; } workspaceCompleteTaskAlias(org, workspace, requestBody)

Renderer-compat alias for /tasks/{id}/complete.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCompleteTaskAliasRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCompleteTaskAliasRequest;

  try {
    const data = await api.workspaceCompleteTaskAlias(body);
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
| **200** | Completed |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateTask

> { [key: string]: any; } workspaceCreateTask(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCreateTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateTaskRequest;

  try {
    const data = await api.workspaceCreateTask(body);
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


## workspaceCreateTaskAlias

> { [key: string]: any; } workspaceCreateTaskAlias(org, workspace, requestBody)

Renderer-compat alias for POST /tasks.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCreateTaskAliasRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateTaskAliasRequest;

  try {
    const data = await api.workspaceCreateTaskAlias(body);
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


## workspaceDeleteTask

> workspaceDeleteTask(org, workspace, id)



### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceDeleteTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceDeleteTaskRequest;

  try {
    const data = await api.workspaceDeleteTask(body);
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


## workspaceGetTask

> { [key: string]: any; } workspaceGetTask(org, workspace, id)



### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetTaskRequest;

  try {
    const data = await api.workspaceGetTask(body);
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
| **200** | Task |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListTaskProviders

> { [key: string]: any; } workspaceListTaskProviders(org, workspace)



### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListTaskProvidersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListTaskProvidersRequest;

  try {
    const data = await api.workspaceListTaskProviders(body);
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


## workspaceListTasks

> { [key: string]: any; } workspaceListTasks(org, workspace)



### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListTasksRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListTasksRequest;

  try {
    const data = await api.workspaceListTasks(body);
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
| **200** | Tasks |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListTasksAlias

> { [key: string]: any; } workspaceListTasksAlias(org, workspace)

Renderer-compat alias for /tasks.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListTasksAliasRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListTasksAliasRequest;

  try {
    const data = await api.workspaceListTasksAlias(body);
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
| **200** | Tasks |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUpdateTask

> { [key: string]: any; } workspaceUpdateTask(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceUpdateTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateTaskRequest;

  try {
    const data = await api.workspaceUpdateTask(body);
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


## workspaceUpdateTaskAlias

> { [key: string]: any; } workspaceUpdateTaskAlias(org, workspace, id, requestBody)

Renderer-compat alias for PATCH /tasks/{id}.

### Example

```ts
import {
  Configuration,
  TasksApi,
} from '@spatio/sdk-ts';
import type { WorkspaceUpdateTaskAliasRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TasksApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateTaskAliasRequest;

  try {
    const data = await api.workspaceUpdateTaskAlias(body);
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

