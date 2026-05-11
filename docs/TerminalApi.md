# TerminalApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTerminalSession**](TerminalApi.md#createterminalsession) | **POST** /v1/terminal/sessions | Create a terminal session record. PTY bytes flow renderer ↔ local-agent over IPC and never traverse this API.  |
| [**deleteTerminalSession**](TerminalApi.md#deleteterminalsession) | **DELETE** /v1/terminal/sessions/{id} | Delete a terminal session record. |
| [**getTerminalSession**](TerminalApi.md#getterminalsession) | **GET** /v1/terminal/sessions/{id} | Fetch a terminal session. |
| [**listTerminalSessions**](TerminalApi.md#listterminalsessions) | **GET** /v1/terminal/sessions | List the caller\&#39;s terminal sessions (metadata only — no PTY bytes). |
| [**updateTerminalSession**](TerminalApi.md#updateterminalsession) | **PATCH** /v1/terminal/sessions/{id} | Update terminal session metadata (title, cwd, etc.). |



## createTerminalSession

> { [key: string]: any; } createTerminalSession(requestBody)

Create a terminal session record. PTY bytes flow renderer ↔ local-agent over IPC and never traverse this API. 

### Example

```ts
import {
  Configuration,
  TerminalApi,
} from '@spatio/sdk-ts';
import type { CreateTerminalSessionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TerminalApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateTerminalSessionRequest;

  try {
    const data = await api.createTerminalSession(body);
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
| **201** | Created session. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteTerminalSession

> deleteTerminalSession(id)

Delete a terminal session record.

### Example

```ts
import {
  Configuration,
  TerminalApi,
} from '@spatio/sdk-ts';
import type { DeleteTerminalSessionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TerminalApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteTerminalSessionRequest;

  try {
    const data = await api.deleteTerminalSession(body);
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


## getTerminalSession

> { [key: string]: any; } getTerminalSession(id)

Fetch a terminal session.

### Example

```ts
import {
  Configuration,
  TerminalApi,
} from '@spatio/sdk-ts';
import type { GetTerminalSessionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TerminalApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetTerminalSessionRequest;

  try {
    const data = await api.getTerminalSession(body);
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Session. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTerminalSessions

> { [key: string]: any; } listTerminalSessions()

List the caller\&#39;s terminal sessions (metadata only — no PTY bytes).

### Example

```ts
import {
  Configuration,
  TerminalApi,
} from '@spatio/sdk-ts';
import type { ListTerminalSessionsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TerminalApi(config);

  try {
    const data = await api.listTerminalSessions();
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Session envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTerminalSession

> { [key: string]: any; } updateTerminalSession(id, requestBody)

Update terminal session metadata (title, cwd, etc.).

### Example

```ts
import {
  Configuration,
  TerminalApi,
} from '@spatio/sdk-ts';
import type { UpdateTerminalSessionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TerminalApi(config);

  const body = {
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies UpdateTerminalSessionRequest;

  try {
    const data = await api.updateTerminalSession(body);
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
| **200** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

