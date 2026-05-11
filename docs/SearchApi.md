# SearchApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**federatedSearch**](SearchApi.md#federatedsearchoperation) | **POST** /v1/search | Cross-platform federated search. |



## federatedSearch

> FederatedSearch200Response federatedSearch(federatedSearchRequest)

Cross-platform federated search.

Fans out to every platform\&#39;s per-platform search method in parallel, merges + dedupes results, and returns them in a relevance-then-recency ranking with per-platform cursors for pagination. 

### Example

```ts
import {
  Configuration,
  SearchApi,
} from '@spatio-labs/spatio-ts';
import type { FederatedSearchOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchApi(config);

  const body = {
    // FederatedSearchRequest
    federatedSearchRequest: ...,
  } satisfies FederatedSearchOperationRequest;

  try {
    const data = await api.federatedSearch(body);
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
| **federatedSearchRequest** | [FederatedSearchRequest](FederatedSearchRequest.md) |  | |

### Return type

[**FederatedSearch200Response**](FederatedSearch200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results. |  -  |
| **400** | Missing query. |  -  |
| **401** | Unauthorized. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

