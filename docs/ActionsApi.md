# ActionsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**executeAction**](ActionsApi.md#executeactionoperation) | **POST** /v1/actions/execute | Renderer-side execute alias. The canonical endpoint is &#x60;POST /v1/agent/actions/execute&#x60;; this path delegates to the same handler.  |
| [**getCoreAction**](ActionsApi.md#getcoreaction) | **GET** /v1/actions/core/{id} | Fetch a single core action by id. |
| [**listAvailableActions**](ActionsApi.md#listavailableactions) | **GET** /v1/actions/available | List every action the agent platform exposes. |
| [**listCoreActions**](ActionsApi.md#listcoreactions) | **GET** /v1/actions/core | List renderer-curated \&quot;core actions\&quot; (command-palette + keybindings backing). |
| [**listCoreActionsByPlatform**](ActionsApi.md#listcoreactionsbyplatform) | **GET** /v1/actions/core/platform/{platform} | Core actions filtered to one platform. |
| [**listPlatformActions**](ActionsApi.md#listplatformactions) | **GET** /v1/actions/platform/{platform} | List actions tagged for a specific platform (notes, mail, ...). |



## executeAction

> ExecuteActionResponse executeAction(executeActionRequest)

Renderer-side execute alias. The canonical endpoint is &#x60;POST /v1/agent/actions/execute&#x60;; this path delegates to the same handler. 

### Example

```ts
import {
  Configuration,
  ActionsApi,
} from '@spatio-labs/spatio-ts';
import type { ExecuteActionOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ActionsApi(config);

  const body = {
    // ExecuteActionRequest
    executeActionRequest: ...,
  } satisfies ExecuteActionOperationRequest;

  try {
    const data = await api.executeAction(body);
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
| **executeActionRequest** | [ExecuteActionRequest](ExecuteActionRequest.md) |  | |

### Return type

[**ExecuteActionResponse**](ExecuteActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Execution result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getCoreAction

> CoreAction getCoreAction(id)

Fetch a single core action by id.

### Example

```ts
import {
  Configuration,
  ActionsApi,
} from '@spatio-labs/spatio-ts';
import type { GetCoreActionRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ActionsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetCoreActionRequest;

  try {
    const data = await api.getCoreAction(body);
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

[**CoreAction**](CoreAction.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Core action. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAvailableActions

> Array&lt;ActionDescriptor&gt; listAvailableActions()

List every action the agent platform exposes.

### Example

```ts
import {
  Configuration,
  ActionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListAvailableActionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ActionsApi(config);

  try {
    const data = await api.listAvailableActions();
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

[**Array&lt;ActionDescriptor&gt;**](ActionDescriptor.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Action descriptors (bare array). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCoreActions

> CoreActionListResponse listCoreActions()

List renderer-curated \&quot;core actions\&quot; (command-palette + keybindings backing).

### Example

```ts
import {
  Configuration,
  ActionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListCoreActionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ActionsApi(config);

  try {
    const data = await api.listCoreActions();
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

[**CoreActionListResponse**](CoreActionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Core action envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCoreActionsByPlatform

> CoreActionListResponse listCoreActionsByPlatform(platform)

Core actions filtered to one platform.

### Example

```ts
import {
  Configuration,
  ActionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListCoreActionsByPlatformRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ActionsApi(config);

  const body = {
    // string
    platform: platform_example,
  } satisfies ListCoreActionsByPlatformRequest;

  try {
    const data = await api.listCoreActionsByPlatform(body);
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
| **platform** | `string` |  | [Defaults to `undefined`] |

### Return type

[**CoreActionListResponse**](CoreActionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Core action envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPlatformActions

> Array&lt;ActionDescriptor&gt; listPlatformActions(platform)

List actions tagged for a specific platform (notes, mail, ...).

### Example

```ts
import {
  Configuration,
  ActionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListPlatformActionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ActionsApi(config);

  const body = {
    // string
    platform: platform_example,
  } satisfies ListPlatformActionsRequest;

  try {
    const data = await api.listPlatformActions(body);
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
| **platform** | `string` |  | [Defaults to `undefined`] |

### Return type

[**Array&lt;ActionDescriptor&gt;**](ActionDescriptor.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Action descriptors (bare array). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

