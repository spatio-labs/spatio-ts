# RealtimeApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**issueCollaborationToken**](RealtimeApi.md#issuecollaborationtokenoperation) | **POST** /v1/realtime/collaboration-token | Exchange a bearer token for a short-lived Yjs collaboration JWT. |



## issueCollaborationToken

> IssueCollaborationToken200Response issueCollaborationToken(issueCollaborationTokenRequest)

Exchange a bearer token for a short-lived Yjs collaboration JWT.

The Yjs Cloudflare Worker that powers live document collaboration (&#x60;wss://realtime-collaboration.&lt;account&gt;.workers.dev&#x60;) only accepts platform-signed JWTs. Third-party clients holding an OAuth access token or PAT call this endpoint to mint a 5-minute collaboration JWT they can present to the worker.  The minted JWT inherits user + workspace identity from the presenting bearer token. Optionally scope it to a single room by supplying &#x60;room&#x60; in the request body. 

### Example

```ts
import {
  Configuration,
  RealtimeApi,
} from '@spatio/sdk-ts';
import type { IssueCollaborationTokenOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RealtimeApi(config);

  const body = {
    // IssueCollaborationTokenRequest (optional)
    issueCollaborationTokenRequest: ...,
  } satisfies IssueCollaborationTokenOperationRequest;

  try {
    const data = await api.issueCollaborationToken(body);
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
| **issueCollaborationTokenRequest** | [IssueCollaborationTokenRequest](IssueCollaborationTokenRequest.md) |  | [Optional] |

### Return type

[**IssueCollaborationToken200Response**](IssueCollaborationToken200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Token issued. |  -  |
| **401** | Bearer token invalid. |  -  |
| **500** | Server misconfigured (JWT_SECRET unset). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

