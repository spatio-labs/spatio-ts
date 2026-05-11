# ConnectionsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**disconnectConnection**](ConnectionsApi.md#disconnectconnectionoperation) | **POST** /v1/connections/disconnect | Disconnect a connected account. |
| [**installConnection**](ConnectionsApi.md#installconnectionoperation) | **POST** /v1/connections/install | Begin an OAuth install for a connection. |
| [**listAccounts**](ConnectionsApi.md#listaccounts) | **GET** /v1/accounts | List the caller\&#39;s multi-provider accounts. |
| [**listConnectionIntegrations**](ConnectionsApi.md#listconnectionintegrations) | **GET** /v1/connections/integrations | List supported integrations + their connection state. Legacy path; &#x60;/v1/connections/list&#x60; is the preferred alias.  |
| [**listConnections**](ConnectionsApi.md#listconnections) | **GET** /v1/connections/list | List supported integrations + their connection state. |
| [**listUserConnections**](ConnectionsApi.md#listuserconnections) | **GET** /v1/connections/user | List the caller\&#39;s connected accounts. |
| [**refreshConnection**](ConnectionsApi.md#refreshconnectionoperation) | **POST** /v1/connections/refresh | Force a refresh of a connection\&#39;s OAuth tokens. |
| [**removeAccount**](ConnectionsApi.md#removeaccount) | **DELETE** /v1/accounts/{accountId} | Remove an account. |
| [**resolveAccount**](ConnectionsApi.md#resolveaccount) | **GET** /v1/accounts/resolve | Resolve an account by provider/identifier. |
| [**syncAccount**](ConnectionsApi.md#syncaccount) | **POST** /v1/accounts/{accountId}/sync | Force a sync against the upstream provider. |
| [**updateAccount**](ConnectionsApi.md#updateaccountoperation) | **PATCH** /v1/accounts/{accountId} | Update account metadata (label, etc.). |



## disconnectConnection

> { [key: string]: any; } disconnectConnection(disconnectConnectionRequest)

Disconnect a connected account.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { DisconnectConnectionOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  const body = {
    // DisconnectConnectionRequest
    disconnectConnectionRequest: ...,
  } satisfies DisconnectConnectionOperationRequest;

  try {
    const data = await api.disconnectConnection(body);
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
| **disconnectConnectionRequest** | [DisconnectConnectionRequest](DisconnectConnectionRequest.md) |  | |

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
| **200** | Result envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## installConnection

> { [key: string]: any; } installConnection(installConnectionRequest)

Begin an OAuth install for a connection.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { InstallConnectionOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  const body = {
    // InstallConnectionRequest
    installConnectionRequest: ...,
  } satisfies InstallConnectionOperationRequest;

  try {
    const data = await api.installConnection(body);
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
| **installConnectionRequest** | [InstallConnectionRequest](InstallConnectionRequest.md) |  | |

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
| **200** | Install result (auth URL or completion). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAccounts

> AccountListResponse listAccounts()

List the caller\&#39;s multi-provider accounts.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListAccountsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  try {
    const data = await api.listAccounts();
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

[**AccountListResponse**](AccountListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listConnectionIntegrations

> ConnectionListResponse listConnectionIntegrations()

List supported integrations + their connection state. Legacy path; &#x60;/v1/connections/list&#x60; is the preferred alias. 

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListConnectionIntegrationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  try {
    const data = await api.listConnectionIntegrations();
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

[**ConnectionListResponse**](ConnectionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connection envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listConnections

> ConnectionListResponse listConnections()

List supported integrations + their connection state.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListConnectionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  try {
    const data = await api.listConnections();
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

[**ConnectionListResponse**](ConnectionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connection envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listUserConnections

> ConnectionAccountListResponse listUserConnections()

List the caller\&#39;s connected accounts.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { ListUserConnectionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  try {
    const data = await api.listUserConnections();
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

[**ConnectionAccountListResponse**](ConnectionAccountListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## refreshConnection

> { [key: string]: any; } refreshConnection(refreshConnectionRequest)

Force a refresh of a connection\&#39;s OAuth tokens.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { RefreshConnectionOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  const body = {
    // RefreshConnectionRequest
    refreshConnectionRequest: ...,
  } satisfies RefreshConnectionOperationRequest;

  try {
    const data = await api.refreshConnection(body);
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
| **refreshConnectionRequest** | [RefreshConnectionRequest](RefreshConnectionRequest.md) |  | |

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
| **200** | Result envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## removeAccount

> removeAccount(accountId)

Remove an account.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { RemoveAccountRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  const body = {
    // string
    accountId: accountId_example,
  } satisfies RemoveAccountRequest;

  try {
    const data = await api.removeAccount(body);
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
| **accountId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Removed. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resolveAccount

> { [key: string]: any; } resolveAccount(provider, email)

Resolve an account by provider/identifier.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { ResolveAccountRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  const body = {
    // string (optional)
    provider: provider_example,
    // string (optional)
    email: email_example,
  } satisfies ResolveAccountRequest;

  try {
    const data = await api.resolveAccount(body);
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
| **provider** | `string` |  | [Optional] [Defaults to `undefined`] |
| **email** | `string` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Account envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## syncAccount

> { [key: string]: any; } syncAccount(accountId)

Force a sync against the upstream provider.

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { SyncAccountRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  const body = {
    // string
    accountId: accountId_example,
  } satisfies SyncAccountRequest;

  try {
    const data = await api.syncAccount(body);
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
| **accountId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Sync result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAccount

> { [key: string]: any; } updateAccount(accountId, updateAccountRequest)

Update account metadata (label, etc.).

### Example

```ts
import {
  Configuration,
  ConnectionsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateAccountOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConnectionsApi(config);

  const body = {
    // string
    accountId: accountId_example,
    // UpdateAccountRequest
    updateAccountRequest: ...,
  } satisfies UpdateAccountOperationRequest;

  try {
    const data = await api.updateAccount(body);
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
| **accountId** | `string` |  | [Defaults to `undefined`] |
| **updateAccountRequest** | [UpdateAccountRequest](UpdateAccountRequest.md) |  | |

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

