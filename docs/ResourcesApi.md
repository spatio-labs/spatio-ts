# ResourcesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listResourcePermissionGrants**](ResourcesApi.md#listresourcepermissiongrants) | **GET** /v1/resources/{platform}/{resourceId}/permissions | List access grants on a resource (per-resource ACL). |
| [**revokeResourcePermissionGrant**](ResourcesApi.md#revokeresourcepermissiongrant) | **DELETE** /v1/resources/{platform}/{resourceId}/permissions/{grantId} | Revoke an access grant. |
| [**setResourcePermissionGrant**](ResourcesApi.md#setresourcepermissiongrant) | **POST** /v1/resources/{platform}/{resourceId}/permissions | Create or update an access grant. |



## listResourcePermissionGrants

> { [key: string]: any; } listResourcePermissionGrants(platform, resourceId)

List access grants on a resource (per-resource ACL).

### Example

```ts
import {
  Configuration,
  ResourcesApi,
} from '@spatio/sdk-ts';
import type { ListResourcePermissionGrantsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ResourcesApi(config);

  const body = {
    // string
    platform: platform_example,
    // string
    resourceId: resourceId_example,
  } satisfies ListResourcePermissionGrantsRequest;

  try {
    const data = await api.listResourcePermissionGrants(body);
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
| **platform** | `string` |  | [Defaults to `undefined`] |
| **resourceId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Grant envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeResourcePermissionGrant

> revokeResourcePermissionGrant(platform, resourceId, grantId)

Revoke an access grant.

### Example

```ts
import {
  Configuration,
  ResourcesApi,
} from '@spatio/sdk-ts';
import type { RevokeResourcePermissionGrantRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ResourcesApi(config);

  const body = {
    // string
    platform: platform_example,
    // string
    resourceId: resourceId_example,
    // string
    grantId: grantId_example,
  } satisfies RevokeResourcePermissionGrantRequest;

  try {
    const data = await api.revokeResourcePermissionGrant(body);
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
| **platform** | `string` |  | [Defaults to `undefined`] |
| **resourceId** | `string` |  | [Defaults to `undefined`] |
| **grantId** | `string` |  | [Defaults to `undefined`] |

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


## setResourcePermissionGrant

> { [key: string]: any; } setResourcePermissionGrant(platform, resourceId, requestBody)

Create or update an access grant.

### Example

```ts
import {
  Configuration,
  ResourcesApi,
} from '@spatio/sdk-ts';
import type { SetResourcePermissionGrantRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ResourcesApi(config);

  const body = {
    // string
    platform: platform_example,
    // string
    resourceId: resourceId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies SetResourcePermissionGrantRequest;

  try {
    const data = await api.setResourcePermissionGrant(body);
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
| **platform** | `string` |  | [Defaults to `undefined`] |
| **resourceId** | `string` |  | [Defaults to `undefined`] |
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

