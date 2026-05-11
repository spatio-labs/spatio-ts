# KeybindingsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteKeyBinding**](KeybindingsApi.md#deletekeybinding) | **DELETE** /v1/keybindings/{id} | Reset a binding to its platform default. |
| [**getDefaultKeyBindings**](KeybindingsApi.md#getdefaultkeybindings) | **GET** /v1/keybindings/defaults | Platform default key bindings (no user customizations applied). |
| [**listKeyBindings**](KeybindingsApi.md#listkeybindings) | **GET** /v1/keybindings | User\&#39;s merged key bindings (defaults + customizations). |
| [**resetAllKeyBindings**](KeybindingsApi.md#resetallkeybindings) | **POST** /v1/keybindings/reset | Reset every customization to its platform default. |
| [**updateKeyBinding**](KeybindingsApi.md#updatekeybindingoperation) | **PUT** /v1/keybindings/{id} | Create or update a user key-binding customization. |
| [**validateKeyBinding**](KeybindingsApi.md#validatekeybindingoperation) | **POST** /v1/keybindings/validate | Check whether a proposed binding conflicts with existing ones. |



## deleteKeyBinding

> deleteKeyBinding(id)

Reset a binding to its platform default.

### Example

```ts
import {
  Configuration,
  KeybindingsApi,
} from '@spatio/sdk-ts';
import type { DeleteKeyBindingRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new KeybindingsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteKeyBindingRequest;

  try {
    const data = await api.deleteKeyBinding(body);
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
| **204** | Reset. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getDefaultKeyBindings

> KeyBindingListResponse getDefaultKeyBindings()

Platform default key bindings (no user customizations applied).

### Example

```ts
import {
  Configuration,
  KeybindingsApi,
} from '@spatio/sdk-ts';
import type { GetDefaultKeyBindingsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new KeybindingsApi(config);

  try {
    const data = await api.getDefaultKeyBindings();
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

[**KeyBindingListResponse**](KeyBindingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Default bindings envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listKeyBindings

> KeyBindingListResponse listKeyBindings()

User\&#39;s merged key bindings (defaults + customizations).

### Example

```ts
import {
  Configuration,
  KeybindingsApi,
} from '@spatio/sdk-ts';
import type { ListKeyBindingsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new KeybindingsApi(config);

  try {
    const data = await api.listKeyBindings();
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

[**KeyBindingListResponse**](KeyBindingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bindings envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resetAllKeyBindings

> resetAllKeyBindings()

Reset every customization to its platform default.

### Example

```ts
import {
  Configuration,
  KeybindingsApi,
} from '@spatio/sdk-ts';
import type { ResetAllKeyBindingsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new KeybindingsApi(config);

  try {
    const data = await api.resetAllKeyBindings();
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


## updateKeyBinding

> KeyBinding updateKeyBinding(id, updateKeyBindingRequest)

Create or update a user key-binding customization.

### Example

```ts
import {
  Configuration,
  KeybindingsApi,
} from '@spatio/sdk-ts';
import type { UpdateKeyBindingOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new KeybindingsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateKeyBindingRequest
    updateKeyBindingRequest: ...,
  } satisfies UpdateKeyBindingOperationRequest;

  try {
    const data = await api.updateKeyBinding(body);
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
| **updateKeyBindingRequest** | [UpdateKeyBindingRequest](UpdateKeyBindingRequest.md) |  | |

### Return type

[**KeyBinding**](KeyBinding.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated binding. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## validateKeyBinding

> ValidateKeyBindingResponse validateKeyBinding(validateKeyBindingRequest)

Check whether a proposed binding conflicts with existing ones.

### Example

```ts
import {
  Configuration,
  KeybindingsApi,
} from '@spatio/sdk-ts';
import type { ValidateKeyBindingOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new KeybindingsApi(config);

  const body = {
    // ValidateKeyBindingRequest
    validateKeyBindingRequest: ...,
  } satisfies ValidateKeyBindingOperationRequest;

  try {
    const data = await api.validateKeyBinding(body);
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
| **validateKeyBindingRequest** | [ValidateKeyBindingRequest](ValidateKeyBindingRequest.md) |  | |

### Return type

[**ValidateKeyBindingResponse**](ValidateKeyBindingResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Validation result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

