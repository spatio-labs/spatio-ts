# PersonalAccessTokensApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createPersonalAccessToken**](PersonalAccessTokensApi.md#createpersonalaccesstoken) | **POST** /v1/tokens | Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again.  |
| [**listAvailablePATScopes**](PersonalAccessTokensApi.md#listavailablepatscopes) | **GET** /v1/tokens/scopes | List the scope strings PATs can be issued with. |
| [**listPersonalAccessTokens**](PersonalAccessTokensApi.md#listpersonalaccesstokens) | **GET** /v1/tokens | List the caller\&#39;s personal access tokens (with available scopes). |
| [**revokePersonalAccessToken**](PersonalAccessTokensApi.md#revokepersonalaccesstoken) | **DELETE** /v1/tokens/{id} | Revoke a PAT. |
| [**updatePersonalAccessToken**](PersonalAccessTokensApi.md#updatepersonalaccesstoken) | **PATCH** /v1/tokens/{id} | Rename or re-describe a PAT (scopes are immutable). |
| [**workspaceCreatePAT**](PersonalAccessTokensApi.md#workspacecreatepat) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tokens |  |
| [**workspaceListPATs**](PersonalAccessTokensApi.md#workspacelistpats) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tokens |  |
| [**workspaceRevokePAT**](PersonalAccessTokensApi.md#workspacerevokepat) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/tokens/{id} |  |
| [**workspaceUpdatePAT**](PersonalAccessTokensApi.md#workspaceupdatepat) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/tokens/{id} |  |



## createPersonalAccessToken

> CreatePATResponse createPersonalAccessToken(createPATRequest)

Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again. 

### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { CreatePersonalAccessTokenRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  const body = {
    // CreatePATRequest
    createPATRequest: ...,
  } satisfies CreatePersonalAccessTokenRequest;

  try {
    const data = await api.createPersonalAccessToken(body);
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
| **createPATRequest** | [CreatePATRequest](CreatePATRequest.md) |  | |

### Return type

[**CreatePATResponse**](CreatePATResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created token (full secret in &#x60;token&#x60;). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAvailablePATScopes

> PATScopesResponse listAvailablePATScopes()

List the scope strings PATs can be issued with.

### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { ListAvailablePATScopesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  try {
    const data = await api.listAvailablePATScopes();
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

[**PATScopesResponse**](PATScopesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Scope list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPersonalAccessTokens

> PATListResponse listPersonalAccessTokens()

List the caller\&#39;s personal access tokens (with available scopes).

### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { ListPersonalAccessTokensRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  try {
    const data = await api.listPersonalAccessTokens();
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

[**PATListResponse**](PATListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | PAT envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokePersonalAccessToken

> revokePersonalAccessToken(id)

Revoke a PAT.

### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { RevokePersonalAccessTokenRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies RevokePersonalAccessTokenRequest;

  try {
    const data = await api.revokePersonalAccessToken(body);
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
| **204** | Revoked. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updatePersonalAccessToken

> PersonalAccessToken updatePersonalAccessToken(id, updatePATRequest)

Rename or re-describe a PAT (scopes are immutable).

### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { UpdatePersonalAccessTokenRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  const body = {
    // string
    id: id_example,
    // UpdatePATRequest
    updatePATRequest: ...,
  } satisfies UpdatePersonalAccessTokenRequest;

  try {
    const data = await api.updatePersonalAccessToken(body);
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
| **updatePATRequest** | [UpdatePATRequest](UpdatePATRequest.md) |  | |

### Return type

[**PersonalAccessToken**](PersonalAccessToken.md)

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


## workspaceCreatePAT

> { [key: string]: any; } workspaceCreatePAT(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceCreatePATRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreatePATRequest;

  try {
    const data = await api.workspaceCreatePAT(body);
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


## workspaceListPATs

> { [key: string]: any; } workspaceListPATs(org, workspace)



### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListPATsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListPATsRequest;

  try {
    const data = await api.workspaceListPATs(body);
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
| **200** | Tokens |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceRevokePAT

> workspaceRevokePAT(org, workspace, id)



### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceRevokePATRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceRevokePATRequest;

  try {
    const data = await api.workspaceRevokePAT(body);
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
| **204** | Revoked |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUpdatePAT

> { [key: string]: any; } workspaceUpdatePAT(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  PersonalAccessTokensApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceUpdatePATRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PersonalAccessTokensApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdatePATRequest;

  try {
    const data = await api.workspaceUpdatePAT(body);
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

