# MiscApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deletePinnedPlatform**](MiscApi.md#deletepinnedplatform) | **DELETE** /v1/pinned-platforms/{platformId} | Unpin a platform. |
| [**getBootstrap**](MiscApi.md#getbootstrap) | **GET** /v1/bootstrap | Single-shot identity + config bundle the renderer hits on first load. Replaces the legacy server-side hydration in app/layout.tsx.  |
| [**getOnboardingInvitations**](MiscApi.md#getonboardinginvitations) | **GET** /v1/onboarding/invitations | Pending invitations the caller can accept during onboarding. |
| [**getPinnedPlatforms**](MiscApi.md#getpinnedplatforms) | **GET** /v1/pinned-platforms | Read the caller\&#39;s pinned-platform list (sidebar order). |
| [**getPlatformPreferences**](MiscApi.md#getplatformpreferences) | **GET** /v1/platform-preferences | Read the caller\&#39;s per-platform sidebar/visibility preferences. |
| [**getPlatformSettingsLegacy**](MiscApi.md#getplatformsettingslegacy) | **GET** /v1/settings/platform | Legacy admin-tier platform settings read endpoint. |
| [**getThreadsStatus**](MiscApi.md#getthreadsstatus) | **GET** /v1/threads/status | Async-thread / job-runner status snapshot. |
| [**getUserPermissions**](MiscApi.md#getuserpermissions) | **GET** /v1/user/permissions | Read the caller\&#39;s effective per-resource permissions. |
| [**getWorkspaceActivity**](MiscApi.md#getworkspaceactivity) | **GET** /v1/workspace-activity | Recent activity feed for a workspace. |
| [**getWorkspaceLayout**](MiscApi.md#getworkspacelayout) | **GET** /v1/layout/{workspaceId} | Read the renderer\&#39;s saved pane layout for a workspace. |
| [**putPinnedPlatform**](MiscApi.md#putpinnedplatform) | **PUT** /v1/pinned-platforms | Pin a platform. |
| [**putPlatformPreferences**](MiscApi.md#putplatformpreferences) | **PUT** /v1/platform-preferences | Replace the caller\&#39;s platform preferences. |
| [**putWorkspaceLayout**](MiscApi.md#putworkspacelayout) | **PUT** /v1/layout/{workspaceId} | Save the renderer\&#39;s pane layout. |
| [**reorderPinnedPlatforms**](MiscApi.md#reorderpinnedplatforms) | **POST** /v1/pinned-platforms/reorder | Reorder the pinned-platform list. |
| [**resetPlatformPreferences**](MiscApi.md#resetplatformpreferences) | **POST** /v1/platform-preferences/reset | Reset platform preferences to defaults. |
| [**updateUserProfile**](MiscApi.md#updateuserprofile) | **PATCH** /v1/user/profile | Update the caller\&#39;s user profile (name, avatar, etc.). |
| [**validateOrganizationSlug**](MiscApi.md#validateorganizationslug) | **GET** /v1/validate-slug/organization | Check whether an org slug is available. |
| [**validateWorkspaceSlug**](MiscApi.md#validateworkspaceslug) | **GET** /v1/validate-slug/workspace | Check whether a workspace slug is available. |



## deletePinnedPlatform

> deletePinnedPlatform(platformId)

Unpin a platform.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { DeletePinnedPlatformRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // string
    platformId: platformId_example,
  } satisfies DeletePinnedPlatformRequest;

  try {
    const data = await api.deletePinnedPlatform(body);
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

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Unpinned. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getBootstrap

> { [key: string]: any; } getBootstrap()

Single-shot identity + config bundle the renderer hits on first load. Replaces the legacy server-side hydration in app/layout.tsx. 

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetBootstrapRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.getBootstrap();
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
| **200** | Bootstrap envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getOnboardingInvitations

> { [key: string]: any; } getOnboardingInvitations()

Pending invitations the caller can accept during onboarding.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetOnboardingInvitationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.getOnboardingInvitations();
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
| **200** | Invitation envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPinnedPlatforms

> { [key: string]: any; } getPinnedPlatforms()

Read the caller\&#39;s pinned-platform list (sidebar order).

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetPinnedPlatformsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.getPinnedPlatforms();
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
| **200** | Pinned platforms. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPlatformPreferences

> { [key: string]: any; } getPlatformPreferences()

Read the caller\&#39;s per-platform sidebar/visibility preferences.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetPlatformPreferencesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.getPlatformPreferences();
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
| **200** | Preferences. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPlatformSettingsLegacy

> { [key: string]: any; } getPlatformSettingsLegacy()

Legacy admin-tier platform settings read endpoint.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetPlatformSettingsLegacyRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.getPlatformSettingsLegacy();
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


## getThreadsStatus

> { [key: string]: any; } getThreadsStatus()

Async-thread / job-runner status snapshot.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetThreadsStatusRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.getThreadsStatus();
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
| **200** | Status envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getUserPermissions

> { [key: string]: any; } getUserPermissions()

Read the caller\&#39;s effective per-resource permissions.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetUserPermissionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.getUserPermissions();
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
| **200** | Permissions envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWorkspaceActivity

> { [key: string]: any; } getWorkspaceActivity(workspaceId, limit)

Recent activity feed for a workspace.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetWorkspaceActivityRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // string (optional)
    workspaceId: workspaceId_example,
    // number (optional)
    limit: 56,
  } satisfies GetWorkspaceActivityRequest;

  try {
    const data = await api.getWorkspaceActivity(body);
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
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Activity envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWorkspaceLayout

> { [key: string]: any; } getWorkspaceLayout(workspaceId)

Read the renderer\&#39;s saved pane layout for a workspace.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { GetWorkspaceLayoutRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
  } satisfies GetWorkspaceLayoutRequest;

  try {
    const data = await api.getWorkspaceLayout(body);
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
| **200** | Layout. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## putPinnedPlatform

> putPinnedPlatform(requestBody)

Pin a platform.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { PutPinnedPlatformRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PutPinnedPlatformRequest;

  try {
    const data = await api.putPinnedPlatform(body);
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
| **204** | Pinned. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## putPlatformPreferences

> putPlatformPreferences(requestBody)

Replace the caller\&#39;s platform preferences.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { PutPlatformPreferencesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PutPlatformPreferencesRequest;

  try {
    const data = await api.putPlatformPreferences(body);
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


## putWorkspaceLayout

> putWorkspaceLayout(workspaceId, requestBody)

Save the renderer\&#39;s pane layout.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { PutWorkspaceLayoutRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PutWorkspaceLayoutRequest;

  try {
    const data = await api.putWorkspaceLayout(body);
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

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Saved. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## reorderPinnedPlatforms

> reorderPinnedPlatforms(requestBody)

Reorder the pinned-platform list.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { ReorderPinnedPlatformsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies ReorderPinnedPlatformsRequest;

  try {
    const data = await api.reorderPinnedPlatforms(body);
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
| **204** | Reordered. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resetPlatformPreferences

> resetPlatformPreferences()

Reset platform preferences to defaults.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { ResetPlatformPreferencesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  try {
    const data = await api.resetPlatformPreferences();
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


## updateUserProfile

> { [key: string]: any; } updateUserProfile(requestBody)

Update the caller\&#39;s user profile (name, avatar, etc.).

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateUserProfileRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies UpdateUserProfileRequest;

  try {
    const data = await api.updateUserProfile(body);
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
| **200** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## validateOrganizationSlug

> { [key: string]: any; } validateOrganizationSlug(slug)

Check whether an org slug is available.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { ValidateOrganizationSlugRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // string (optional)
    slug: slug_example,
  } satisfies ValidateOrganizationSlugRequest;

  try {
    const data = await api.validateOrganizationSlug(body);
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
| **slug** | `string` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Validation result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## validateWorkspaceSlug

> { [key: string]: any; } validateWorkspaceSlug(slug, organizationId)

Check whether a workspace slug is available.

### Example

```ts
import {
  Configuration,
  MiscApi,
} from '@spatio-labs/spatio-ts';
import type { ValidateWorkspaceSlugRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MiscApi(config);

  const body = {
    // string (optional)
    slug: slug_example,
    // string (optional)
    organizationId: organizationId_example,
  } satisfies ValidateWorkspaceSlugRequest;

  try {
    const data = await api.validateWorkspaceSlug(body);
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
| **slug** | `string` |  | [Optional] [Defaults to `undefined`] |
| **organizationId** | `string` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Validation result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

