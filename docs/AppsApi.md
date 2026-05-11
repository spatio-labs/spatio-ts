# AppsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createApp**](AppsApi.md#createappoperation) | **POST** /v1/apps | Register a prototype app (project_path is the on-disk root). |
| [**deleteApp**](AppsApi.md#deleteapp) | **DELETE** /v1/apps/{id} | Delete an app. |
| [**deleteAppFile**](AppsApi.md#deleteappfile) | **DELETE** /v1/apps/{id}/file | Delete one file inside the app\&#39;s project directory. |
| [**getApp**](AppsApi.md#getapp) | **GET** /v1/apps/{id} | Fetch an app. |
| [**listAppFiles**](AppsApi.md#listappfiles) | **GET** /v1/apps/{id}/files | List files inside the app\&#39;s project directory. |
| [**listApps**](AppsApi.md#listapps) | **GET** /v1/apps | List the caller\&#39;s prototype apps. |
| [**readAppFile**](AppsApi.md#readappfile) | **GET** /v1/apps/{id}/file | Read one file inside the app\&#39;s project directory. Path is traversal-checked; returns 400 if it escapes project root.  |
| [**updateApp**](AppsApi.md#updateappoperation) | **PATCH** /v1/apps/{id} | Update an app. |
| [**workspaceCreateApp**](AppsApi.md#workspacecreateapp) | **POST** /v1/organizations/{org}/workspaces/{workspace}/apps |  |
| [**workspaceDeleteApp**](AppsApi.md#workspacedeleteapp) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/apps/{id} |  |
| [**workspaceGetApp**](AppsApi.md#workspacegetapp) | **GET** /v1/organizations/{org}/workspaces/{workspace}/apps/{id} |  |
| [**workspaceListApps**](AppsApi.md#workspacelistapps) | **GET** /v1/organizations/{org}/workspaces/{workspace}/apps |  |
| [**workspaceUpdateApp**](AppsApi.md#workspaceupdateapp) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/apps/{id} |  |
| [**writeAppFile**](AppsApi.md#writeappfileoperation) | **POST** /v1/apps/{id}/file | Write one file inside the app\&#39;s project directory. |



## createApp

> App createApp(createAppRequest)

Register a prototype app (project_path is the on-disk root).

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { CreateAppOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // CreateAppRequest
    createAppRequest: ...,
  } satisfies CreateAppOperationRequest;

  try {
    const data = await api.createApp(body);
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
| **createAppRequest** | [CreateAppRequest](CreateAppRequest.md) |  | |

### Return type

[**App**](App.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created app. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteApp

> deleteApp(id)

Delete an app.

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { DeleteAppRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteAppRequest;

  try {
    const data = await api.deleteApp(body);
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
| **204** | Deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAppFile

> deleteAppFile(id, path)

Delete one file inside the app\&#39;s project directory.

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { DeleteAppFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    id: id_example,
    // string
    path: path_example,
  } satisfies DeleteAppFileRequest;

  try {
    const data = await api.deleteAppFile(body);
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
| **path** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getApp

> App getApp(id)

Fetch an app.

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { GetAppRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetAppRequest;

  try {
    const data = await api.getApp(body);
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

[**App**](App.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | App. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAppFiles

> AppFileListResponse listAppFiles(id, path)

List files inside the app\&#39;s project directory.

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { ListAppFilesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    id: id_example,
    // string (optional)
    path: path_example,
  } satisfies ListAppFilesRequest;

  try {
    const data = await api.listAppFiles(body);
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
| **path** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**AppFileListResponse**](AppFileListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | File envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listApps

> AppListResponse listApps()

List the caller\&#39;s prototype apps.

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { ListAppsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  try {
    const data = await api.listApps();
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

[**AppListResponse**](AppListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | App envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## readAppFile

> AppFileContentResponse readAppFile(id, path)

Read one file inside the app\&#39;s project directory. Path is traversal-checked; returns 400 if it escapes project root. 

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { ReadAppFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    id: id_example,
    // string
    path: path_example,
  } satisfies ReadAppFileRequest;

  try {
    const data = await api.readAppFile(body);
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
| **path** | `string` |  | [Defaults to `undefined`] |

### Return type

[**AppFileContentResponse**](AppFileContentResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | File content. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateApp

> App updateApp(id, updateAppRequest)

Update an app.

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { UpdateAppOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateAppRequest
    updateAppRequest: ...,
  } satisfies UpdateAppOperationRequest;

  try {
    const data = await api.updateApp(body);
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
| **updateAppRequest** | [UpdateAppRequest](UpdateAppRequest.md) |  | |

### Return type

[**App**](App.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateApp

> { [key: string]: any; } workspaceCreateApp(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCreateAppRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateAppRequest;

  try {
    const data = await api.workspaceCreateApp(body);
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


## workspaceDeleteApp

> workspaceDeleteApp(org, workspace, id)



### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { WorkspaceDeleteAppRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceDeleteAppRequest;

  try {
    const data = await api.workspaceDeleteApp(body);
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


## workspaceGetApp

> { [key: string]: any; } workspaceGetApp(org, workspace, id)



### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetAppRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetAppRequest;

  try {
    const data = await api.workspaceGetApp(body);
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
| **200** | App |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListApps

> { [key: string]: any; } workspaceListApps(org, workspace)



### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListAppsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListAppsRequest;

  try {
    const data = await api.workspaceListApps(body);
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
| **200** | Apps |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUpdateApp

> { [key: string]: any; } workspaceUpdateApp(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { WorkspaceUpdateAppRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateAppRequest;

  try {
    const data = await api.workspaceUpdateApp(body);
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


## writeAppFile

> writeAppFile(id, writeAppFileRequest)

Write one file inside the app\&#39;s project directory.

### Example

```ts
import {
  Configuration,
  AppsApi,
} from '@spatio/sdk-ts';
import type { WriteAppFileOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AppsApi(config);

  const body = {
    // string
    id: id_example,
    // WriteAppFileRequest
    writeAppFileRequest: ...,
  } satisfies WriteAppFileOperationRequest;

  try {
    const data = await api.writeAppFile(body);
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
| **writeAppFileRequest** | [WriteAppFileRequest](WriteAppFileRequest.md) |  | |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Written. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

