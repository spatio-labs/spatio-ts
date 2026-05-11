# RecommendationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteRecommendation**](RecommendationsApi.md#deleterecommendation) | **DELETE** /v1/recommendations/{id} | Delete a recommendation (hard delete; status-update is preferred). |
| [**getRecommendation**](RecommendationsApi.md#getrecommendation) | **GET** /v1/recommendations/{id} | Fetch one recommendation. |
| [**listRecommendations**](RecommendationsApi.md#listrecommendations) | **GET** /v1/recommendations | List recommendations for a workspace. |
| [**proposeRecommendation**](RecommendationsApi.md#proposerecommendationoperation) | **POST** /v1/recommendations | Agent-side propose endpoint (the &#x60;spatio_recommendations propose&#x60; MCP tool calls this). |
| [**updateRecommendationStatus**](RecommendationsApi.md#updaterecommendationstatusoperation) | **PATCH** /v1/recommendations/{id}/status | Accept or dismiss a recommendation. |



## deleteRecommendation

> deleteRecommendation(id)

Delete a recommendation (hard delete; status-update is preferred).

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteRecommendationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteRecommendationRequest;

  try {
    const data = await api.deleteRecommendation(body);
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


## getRecommendation

> Recommendation getRecommendation(id)

Fetch one recommendation.

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@spatio-labs/spatio-ts';
import type { GetRecommendationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetRecommendationRequest;

  try {
    const data = await api.getRecommendation(body);
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

[**Recommendation**](Recommendation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recommendation. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRecommendations

> RecommendationListResponse listRecommendations(workspaceId, status, limit)

List recommendations for a workspace.

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@spatio-labs/spatio-ts';
import type { ListRecommendationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // string (optional)
    workspaceId: workspaceId_example,
    // string (optional)
    status: status_example,
    // number (optional)
    limit: 56,
  } satisfies ListRecommendationsRequest;

  try {
    const data = await api.listRecommendations(body);
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
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**RecommendationListResponse**](RecommendationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recommendation list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## proposeRecommendation

> Recommendation proposeRecommendation(proposeRecommendationRequest)

Agent-side propose endpoint (the &#x60;spatio_recommendations propose&#x60; MCP tool calls this).

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@spatio-labs/spatio-ts';
import type { ProposeRecommendationOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // ProposeRecommendationRequest
    proposeRecommendationRequest: ...,
  } satisfies ProposeRecommendationOperationRequest;

  try {
    const data = await api.proposeRecommendation(body);
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
| **proposeRecommendationRequest** | [ProposeRecommendationRequest](ProposeRecommendationRequest.md) |  | |

### Return type

[**Recommendation**](Recommendation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Proposed recommendation. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateRecommendationStatus

> Recommendation updateRecommendationStatus(id, updateRecommendationStatusRequest)

Accept or dismiss a recommendation.

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateRecommendationStatusOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateRecommendationStatusRequest
    updateRecommendationStatusRequest: ...,
  } satisfies UpdateRecommendationStatusOperationRequest;

  try {
    const data = await api.updateRecommendationStatus(body);
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
| **updateRecommendationStatusRequest** | [UpdateRecommendationStatusRequest](UpdateRecommendationStatusRequest.md) |  | |

### Return type

[**Recommendation**](Recommendation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated recommendation. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

