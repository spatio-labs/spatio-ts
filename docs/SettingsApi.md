# SettingsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**bulkUpdateSettings**](SettingsApi.md#bulkupdatesettings) | **POST** /v1/settings/bulk-update | Bulk-update multiple settings rows in one round-trip. |
| [**deleteCurrentUserSettings**](SettingsApi.md#deletecurrentusersettings) | **DELETE** /v1/settings | Reset the caller\&#39;s user-level settings. |
| [**getCurrentUserSettings**](SettingsApi.md#getcurrentusersettings) | **GET** /v1/settings | Fetch the caller\&#39;s user-level settings. |
| [**getMailReadReceiptsPref**](SettingsApi.md#getmailreadreceiptspref) | **GET** /v1/me/preferences/mail-read-receipts | Read the caller\&#39;s mail-read-receipts preference. |
| [**getSettingsPermissions**](SettingsApi.md#getsettingspermissions) | **GET** /v1/settings/permissions | Read the caller\&#39;s settings-write permissions matrix. |
| [**getUserSettings**](SettingsApi.md#getusersettings) | **GET** /v1/settings/user/{userId} | Fetch a specific user\&#39;s settings (admin / self only). |
| [**getWorkspaceSettings**](SettingsApi.md#getworkspacesettings) | **GET** /v1/settings/workspace/{workspaceId} | Fetch workspace-level settings. |
| [**putCurrentUserSettings**](SettingsApi.md#putcurrentusersettings) | **PUT** /v1/settings | Replace the caller\&#39;s user-level settings. |
| [**putMailReadReceiptsPref**](SettingsApi.md#putmailreadreceiptspref) | **PUT** /v1/me/preferences/mail-read-receipts | Update the caller\&#39;s mail-read-receipts preference. |
| [**putUserSettings**](SettingsApi.md#putusersettings) | **PUT** /v1/settings/user/{userId} | Replace a specific user\&#39;s settings. |
| [**putWorkspaceSettings**](SettingsApi.md#putworkspacesettings) | **PUT** /v1/settings/workspace/{workspaceId} | Replace workspace-level settings. |



## bulkUpdateSettings

> { [key: string]: any; } bulkUpdateSettings(requestBody)

Bulk-update multiple settings rows in one round-trip.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { BulkUpdateSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies BulkUpdateSettingsRequest;

  try {
    const data = await api.bulkUpdateSettings(body);
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
| **200** | Result envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteCurrentUserSettings

> deleteCurrentUserSettings()

Reset the caller\&#39;s user-level settings.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteCurrentUserSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  try {
    const data = await api.deleteCurrentUserSettings();
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

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Reset. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getCurrentUserSettings

> { [key: string]: any; } getCurrentUserSettings()

Fetch the caller\&#39;s user-level settings.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { GetCurrentUserSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  try {
    const data = await api.getCurrentUserSettings();
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
| **200** | Settings. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMailReadReceiptsPref

> { [key: string]: any; } getMailReadReceiptsPref()

Read the caller\&#39;s mail-read-receipts preference.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { GetMailReadReceiptsPrefRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  try {
    const data = await api.getMailReadReceiptsPref();
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
| **200** | Preference. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSettingsPermissions

> { [key: string]: any; } getSettingsPermissions()

Read the caller\&#39;s settings-write permissions matrix.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { GetSettingsPermissionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  try {
    const data = await api.getSettingsPermissions();
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
| **200** | Permissions. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getUserSettings

> { [key: string]: any; } getUserSettings(userId)

Fetch a specific user\&#39;s settings (admin / self only).

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { GetUserSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  const body = {
    // string
    userId: userId_example,
  } satisfies GetUserSettingsRequest;

  try {
    const data = await api.getUserSettings(body);
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
| **userId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Settings. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWorkspaceSettings

> { [key: string]: any; } getWorkspaceSettings(workspaceId)

Fetch workspace-level settings.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { GetWorkspaceSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
  } satisfies GetWorkspaceSettingsRequest;

  try {
    const data = await api.getWorkspaceSettings(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Settings. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## putCurrentUserSettings

> { [key: string]: any; } putCurrentUserSettings(requestBody)

Replace the caller\&#39;s user-level settings.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { PutCurrentUserSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PutCurrentUserSettingsRequest;

  try {
    const data = await api.putCurrentUserSettings(body);
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
| **200** | Updated settings. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## putMailReadReceiptsPref

> putMailReadReceiptsPref(requestBody)

Update the caller\&#39;s mail-read-receipts preference.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { PutMailReadReceiptsPrefRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PutMailReadReceiptsPrefRequest;

  try {
    const data = await api.putMailReadReceiptsPref(body);
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

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## putUserSettings

> { [key: string]: any; } putUserSettings(userId, requestBody)

Replace a specific user\&#39;s settings.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { PutUserSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  const body = {
    // string
    userId: userId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PutUserSettingsRequest;

  try {
    const data = await api.putUserSettings(body);
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
| **userId** | `string` |  | [Defaults to `undefined`] |
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


## putWorkspaceSettings

> { [key: string]: any; } putWorkspaceSettings(workspaceId, requestBody)

Replace workspace-level settings.

### Example

```ts
import {
  Configuration,
  SettingsApi,
} from '@spatio-labs/spatio-ts';
import type { PutWorkspaceSettingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SettingsApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PutWorkspaceSettingsRequest;

  try {
    const data = await api.putWorkspaceSettings(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |
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

