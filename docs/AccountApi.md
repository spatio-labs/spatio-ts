# AccountApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**changePassword**](AccountApi.md#changepasswordoperation) | **POST** /v1/account/security/password | Change or set the account password. |
| [**consumeAgentTask**](AccountApi.md#consumeagenttask) | **POST** /v1/account/usage/consume-agent-task | Atomic check + increment on the agent-task counter (one slot per turn). |
| [**getAccountPlan**](AccountApi.md#getaccountplan) | **GET** /v1/account/plan | The caller\&#39;s subscription tier and status. |
| [**getAccountTier**](AccountApi.md#getaccounttier) | **GET** /v1/account/tier | Capability + quota envelope for the caller\&#39;s tier. |
| [**getAccountUsage**](AccountApi.md#getaccountusage) | **GET** /v1/account/usage | Today\&#39;s usage counters across notes, sheets, slides, files, tasks, mail, API. |
| [**getAgentTaskUsage**](AccountApi.md#getagenttaskusage) | **GET** /v1/account/usage/agent-tasks | Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST &#x60;/v1/account/usage/consume-agent-task&#x60; atomically per turn to gate a tool-using turn.  |
| [**getSignInMethods**](AccountApi.md#getsigninmethods) | **GET** /v1/account/security/sign-in-methods | List the linked sign-in methods (password + OAuth providers). |
| [**listConnectedApps**](AccountApi.md#listconnectedapps) | **GET** /v1/account/connected-apps | List the OAuth clients the calling user has granted access to. |
| [**listSessions**](AccountApi.md#listsessions) | **GET** /v1/account/security/sessions | List active sessions for the caller. |
| [**revokeConnectedApp**](AccountApi.md#revokeconnectedapp) | **DELETE** /v1/account/connected-apps/{client_id} | Revoke a connected app and all of its active tokens. |
| [**revokeOtherSessions**](AccountApi.md#revokeothersessions) | **POST** /v1/account/security/sessions/revoke-others | Revoke every session except the caller\&#39;s current one. |
| [**revokeSession**](AccountApi.md#revokesession) | **DELETE** /v1/account/security/sessions/{id} | Revoke a specific session. |



## changePassword

> changePassword(changePasswordRequest)

Change or set the account password.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { ChangePasswordOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  const body = {
    // ChangePasswordRequest
    changePasswordRequest: ...,
  } satisfies ChangePasswordOperationRequest;

  try {
    const data = await api.changePassword(body);
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
| **changePasswordRequest** | [ChangePasswordRequest](ChangePasswordRequest.md) |  | |

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
| **204** | Password updated. |  -  |
| **400** | Invalid body or password too weak. |  -  |
| **401** | Caller is not authenticated, or &#x60;currentPassword&#x60; is wrong. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## consumeAgentTask

> ConsumeAgentTaskResponse consumeAgentTask()

Atomic check + increment on the agent-task counter (one slot per turn).

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { ConsumeAgentTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.consumeAgentTask();
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

[**ConsumeAgentTaskResponse**](ConsumeAgentTaskResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Slot consumed. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **402** | Free trial expired (&#x60;trial_expired&#x60;). |  -  |
| **429** | Daily agent-task limit exceeded. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAccountPlan

> AccountPlan getAccountPlan()

The caller\&#39;s subscription tier and status.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { GetAccountPlanRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.getAccountPlan();
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

[**AccountPlan**](AccountPlan.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Plan summary. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAccountTier

> AccountTierDetails getAccountTier()

Capability + quota envelope for the caller\&#39;s tier.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { GetAccountTierRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.getAccountTier();
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

[**AccountTierDetails**](AccountTierDetails.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tier details. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAccountUsage

> AccountUsage getAccountUsage()

Today\&#39;s usage counters across notes, sheets, slides, files, tasks, mail, API.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { GetAccountUsageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.getAccountUsage();
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

[**AccountUsage**](AccountUsage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Usage snapshot. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAgentTaskUsage

> AgentTaskUsage getAgentTaskUsage()

Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST &#x60;/v1/account/usage/consume-agent-task&#x60; atomically per turn to gate a tool-using turn. 

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { GetAgentTaskUsageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.getAgentTaskUsage();
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

[**AgentTaskUsage**](AgentTaskUsage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Counter snapshot. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSignInMethods

> SignInMethods getSignInMethods()

List the linked sign-in methods (password + OAuth providers).

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { GetSignInMethodsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.getSignInMethods();
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

[**SignInMethods**](SignInMethods.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sign-in methods. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listConnectedApps

> ConnectedAppsListResponse listConnectedApps()

List the OAuth clients the calling user has granted access to.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { ListConnectedAppsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.listConnectedApps();
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

[**ConnectedAppsListResponse**](ConnectedAppsListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Grants. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSessions

> SessionListResponse listSessions()

List active sessions for the caller.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { ListSessionsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.listSessions();
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

[**SessionListResponse**](SessionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Session list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeConnectedApp

> revokeConnectedApp(clientId)

Revoke a connected app and all of its active tokens.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { RevokeConnectedAppRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  const body = {
    // string
    clientId: clientId_example,
  } satisfies RevokeConnectedAppRequest;

  try {
    const data = await api.revokeConnectedApp(body);
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
| **clientId** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Revoked. |  -  |
| **404** | No active grant for that client. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeOtherSessions

> RevokeOtherSessionsResponse revokeOtherSessions()

Revoke every session except the caller\&#39;s current one.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { RevokeOtherSessionsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  try {
    const data = await api.revokeOtherSessions();
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

[**RevokeOtherSessionsResponse**](RevokeOtherSessionsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Count of sessions revoked. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeSession

> revokeSession(id)

Revoke a specific session.

### Example

```ts
import {
  Configuration,
  AccountApi,
} from '@spatio/sdk-ts';
import type { RevokeSessionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccountApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies RevokeSessionRequest;

  try {
    const data = await api.revokeSession(body);
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
| **204** | Session revoked. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Session not found or not owned by caller. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

