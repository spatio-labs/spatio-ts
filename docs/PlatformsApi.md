# PlatformsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addPlatformProviderAccount**](PlatformsApi.md#addplatformprovideraccount) | **POST** /v1/platforms/{platformId}/providers/{provider}/accounts | Add a connected account for a platform/provider pair. |
| [**createOrUpdatePlatformSecret**](PlatformsApi.md#createorupdateplatformsecret) | **POST** /v1/platforms/{platformId}/secrets | Create or update a secret value. |
| [**deletePlatformSecret**](PlatformsApi.md#deleteplatformsecret) | **DELETE** /v1/platforms/{platformId}/secrets/{name} | Delete a secret. |
| [**execPlatformData**](PlatformsApi.md#execplatformdata) | **POST** /v1/platforms/{platformId}/exec | Run an INSERT/UPDATE/DELETE statement against a platform\&#39;s store. |
| [**exportPlatformSecrets**](PlatformsApi.md#exportplatformsecrets) | **GET** /v1/platforms/{platformId}/secrets/export | Export all secrets for a platform (values included). Caller must be the platform owner.  |
| [**generatePlatformBackendToken**](PlatformsApi.md#generateplatformbackendtoken) | **POST** /v1/platforms/{platformId}/backend-token | Generate a short-lived backend JWT a platform\&#39;s worker can use to call back into platform-service.  |
| [**getPlatformCatalog**](PlatformsApi.md#getplatformcatalog) | **GET** /v1/catalog/platforms | List the global platform catalog — every platform that exists, not just the ones the caller has installed.  |
| [**getPlatformManifest**](PlatformsApi.md#getplatformmanifest) | **GET** /v1/platforms/{platformId}/manifest | Fetch a platform\&#39;s manifest (capabilities, schema, UI metadata). |
| [**listPlatformAccounts**](PlatformsApi.md#listplatformaccounts) | **GET** /v1/platforms/{platformId}/accounts | List accounts the caller has connected for a platform. |
| [**listPlatformProviders**](PlatformsApi.md#listplatformproviders) | **GET** /v1/platforms/{platformId}/providers | Discover supported providers + capabilities for a platform. |
| [**listPlatformSecrets**](PlatformsApi.md#listplatformsecrets) | **GET** /v1/platforms/{platformId}/secrets | List secret keys (values redacted). |
| [**listPlatformTables**](PlatformsApi.md#listplatformtables) | **GET** /v1/platforms/{platformId}/tables | List tables in a platform\&#39;s data store. |
| [**listPlatforms**](PlatformsApi.md#listplatforms) | **GET** /v1/platforms | List installed platforms for the sidebar. |
| [**queryPlatformData**](PlatformsApi.md#queryplatformdata) | **POST** /v1/platforms/{platformId}/query | Run a SELECT query against a platform\&#39;s data store. |
| [**runPlatformMigrations**](PlatformsApi.md#runplatformmigrations) | **POST** /v1/platforms/{platformId}/migrate | Run pending migrations for a platform. |



## addPlatformProviderAccount

> { [key: string]: any; } addPlatformProviderAccount(platformId, provider, requestBody)

Add a connected account for a platform/provider pair.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { AddPlatformProviderAccountRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
    // string
    provider: provider_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies AddPlatformProviderAccountRequest;

  try {
    const data = await api.addPlatformProviderAccount(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |
| **provider** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Created account. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createOrUpdatePlatformSecret

> { [key: string]: any; } createOrUpdatePlatformSecret(platformId, requestBody)

Create or update a secret value.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateOrUpdatePlatformSecretRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateOrUpdatePlatformSecretRequest;

  try {
    const data = await api.createOrUpdatePlatformSecret(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Created/updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deletePlatformSecret

> deletePlatformSecret(platformId, name)

Delete a secret.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { DeletePlatformSecretRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
    // string
    name: name_example,
  } satisfies DeletePlatformSecretRequest;

  try {
    const data = await api.deletePlatformSecret(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |
| **name** | `string` |  | [Defaults to `undefined`] |

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


## execPlatformData

> { [key: string]: any; } execPlatformData(platformId, requestBody)

Run an INSERT/UPDATE/DELETE statement against a platform\&#39;s store.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { ExecPlatformDataRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies ExecPlatformDataRequest;

  try {
    const data = await api.execPlatformData(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Execution result (rows affected, etc.). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## exportPlatformSecrets

> { [key: string]: any; } exportPlatformSecrets(platformId)

Export all secrets for a platform (values included). Caller must be the platform owner. 

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { ExportPlatformSecretsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies ExportPlatformSecretsRequest;

  try {
    const data = await api.exportPlatformSecrets(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Exported secrets. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## generatePlatformBackendToken

> { [key: string]: any; } generatePlatformBackendToken(platformId)

Generate a short-lived backend JWT a platform\&#39;s worker can use to call back into platform-service. 

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { GeneratePlatformBackendTokenRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies GeneratePlatformBackendTokenRequest;

  try {
    const data = await api.generatePlatformBackendToken(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Backend token. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPlatformCatalog

> { [key: string]: any; } getPlatformCatalog()

List the global platform catalog — every platform that exists, not just the ones the caller has installed. 

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { GetPlatformCatalogRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  try {
    const data = await api.getPlatformCatalog();
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
| **200** | Catalog envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPlatformManifest

> { [key: string]: any; } getPlatformManifest(platformId)

Fetch a platform\&#39;s manifest (capabilities, schema, UI metadata).

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { GetPlatformManifestRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies GetPlatformManifestRequest;

  try {
    const data = await api.getPlatformManifest(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Manifest. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPlatformAccounts

> { [key: string]: any; } listPlatformAccounts(platformId)

List accounts the caller has connected for a platform.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { ListPlatformAccountsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies ListPlatformAccountsRequest;

  try {
    const data = await api.listPlatformAccounts(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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


## listPlatformProviders

> { [key: string]: any; } listPlatformProviders(platformId)

Discover supported providers + capabilities for a platform.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { ListPlatformProvidersRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies ListPlatformProvidersRequest;

  try {
    const data = await api.listPlatformProviders(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Provider envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPlatformSecrets

> { [key: string]: any; } listPlatformSecrets(platformId)

List secret keys (values redacted).

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { ListPlatformSecretsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies ListPlatformSecretsRequest;

  try {
    const data = await api.listPlatformSecrets(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Secret envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPlatformTables

> { [key: string]: any; } listPlatformTables(platformId)

List tables in a platform\&#39;s data store.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { ListPlatformTablesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies ListPlatformTablesRequest;

  try {
    const data = await api.listPlatformTables(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Table envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPlatforms

> { [key: string]: any; } listPlatforms()

List installed platforms for the sidebar.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { ListPlatformsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  try {
    const data = await api.listPlatforms();
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
| **200** | Platform envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## queryPlatformData

> { [key: string]: any; } queryPlatformData(platformId, requestBody)

Run a SELECT query against a platform\&#39;s data store.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { QueryPlatformDataRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies QueryPlatformDataRequest;

  try {
    const data = await api.queryPlatformData(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Query result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## runPlatformMigrations

> { [key: string]: any; } runPlatformMigrations(platformId)

Run pending migrations for a platform.

### Example

```ts
import {
  Configuration,
  PlatformsApi,
} from '@spatio-labs/spatio-ts';
import type { RunPlatformMigrationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PlatformsApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies RunPlatformMigrationsRequest;

  try {
    const data = await api.runPlatformMigrations(body);
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
| **platformId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Migration result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

