# RoutinesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**claimRoutineRun**](RoutinesApi.md#claimroutinerun) | **POST** /v1/routines/runs/{id}/claim | Worker claims a queued run. |
| [**completeRoutineRun**](RoutinesApi.md#completeroutinerun) | **POST** /v1/routines/runs/{id}/complete | Worker marks a run complete. |
| [**createRoutine**](RoutinesApi.md#createroutineoperation) | **POST** /v1/routines | Create a routine. |
| [**deleteRoutine**](RoutinesApi.md#deleteroutine) | **DELETE** /v1/routines/{id} | Delete a routine. |
| [**getRoutine**](RoutinesApi.md#getroutine) | **GET** /v1/routines/{id} | Fetch a routine. |
| [**listRoutineRuns**](RoutinesApi.md#listroutineruns) | **GET** /v1/routines/{id}/runs | List runs for a routine. |
| [**listRoutines**](RoutinesApi.md#listroutines) | **GET** /v1/routines | List routines for the caller\&#39;s workspace. |
| [**runRoutineNow**](RoutinesApi.md#runroutinenow) | **POST** /v1/routines/{id}/run-now | Trigger an ad-hoc run. |
| [**updateRoutine**](RoutinesApi.md#updateroutineoperation) | **PATCH** /v1/routines/{id} | Update a routine. |
| [**updateRoutineRunProgress**](RoutinesApi.md#updateroutinerunprogress) | **POST** /v1/routines/runs/{id}/progress | Worker reports progress. |



## claimRoutineRun

> RoutineRun claimRoutineRun(id)

Worker claims a queued run.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { ClaimRoutineRunRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies ClaimRoutineRunRequest;

  try {
    const data = await api.claimRoutineRun(body);
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

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Claimed run. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## completeRoutineRun

> RoutineRun completeRoutineRun(id, routineRunCompleteRequest)

Worker marks a run complete.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { CompleteRoutineRunRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
    // RoutineRunCompleteRequest
    routineRunCompleteRequest: ...,
  } satisfies CompleteRoutineRunRequest;

  try {
    const data = await api.completeRoutineRun(body);
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
| **routineRunCompleteRequest** | [RoutineRunCompleteRequest](RoutineRunCompleteRequest.md) |  | |

### Return type

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Completed run. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createRoutine

> Routine createRoutine(createRoutineRequest)

Create a routine.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { CreateRoutineOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // CreateRoutineRequest
    createRoutineRequest: ...,
  } satisfies CreateRoutineOperationRequest;

  try {
    const data = await api.createRoutine(body);
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
| **createRoutineRequest** | [CreateRoutineRequest](CreateRoutineRequest.md) |  | |

### Return type

[**Routine**](Routine.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteRoutine

> deleteRoutine(id)

Delete a routine.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { DeleteRoutineRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteRoutineRequest;

  try {
    const data = await api.deleteRoutine(body);
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


## getRoutine

> Routine getRoutine(id)

Fetch a routine.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { GetRoutineRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetRoutineRequest;

  try {
    const data = await api.getRoutine(body);
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

[**Routine**](Routine.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Routine. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRoutineRuns

> RoutineRunListResponse listRoutineRuns(id)

List runs for a routine.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { ListRoutineRunsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies ListRoutineRunsRequest;

  try {
    const data = await api.listRoutineRuns(body);
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

[**RoutineRunListResponse**](RoutineRunListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Run envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRoutines

> RoutineListResponse listRoutines(workspaceId, status)

List routines for the caller\&#39;s workspace.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { ListRoutinesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string (optional)
    workspaceId: workspaceId_example,
    // string (optional)
    status: status_example,
  } satisfies ListRoutinesRequest;

  try {
    const data = await api.listRoutines(body);
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
| **workspaceId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **status** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**RoutineListResponse**](RoutineListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Routine envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## runRoutineNow

> RoutineRun runRoutineNow(id)

Trigger an ad-hoc run.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { RunRoutineNowRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies RunRoutineNowRequest;

  try {
    const data = await api.runRoutineNow(body);
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

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Created run. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateRoutine

> Routine updateRoutine(id, updateRoutineRequest)

Update a routine.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { UpdateRoutineOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateRoutineRequest
    updateRoutineRequest: ...,
  } satisfies UpdateRoutineOperationRequest;

  try {
    const data = await api.updateRoutine(body);
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
| **updateRoutineRequest** | [UpdateRoutineRequest](UpdateRoutineRequest.md) |  | |

### Return type

[**Routine**](Routine.md)

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


## updateRoutineRunProgress

> RoutineRun updateRoutineRunProgress(id, routineRunProgressRequest)

Worker reports progress.

### Example

```ts
import {
  Configuration,
  RoutinesApi,
} from '@spatio/sdk-ts';
import type { UpdateRoutineRunProgressRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RoutinesApi(config);

  const body = {
    // string
    id: id_example,
    // RoutineRunProgressRequest
    routineRunProgressRequest: ...,
  } satisfies UpdateRoutineRunProgressRequest;

  try {
    const data = await api.updateRoutineRunProgress(body);
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
| **routineRunProgressRequest** | [RoutineRunProgressRequest](RoutineRunProgressRequest.md) |  | |

### Return type

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated run. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

