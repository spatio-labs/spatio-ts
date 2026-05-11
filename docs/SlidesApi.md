# SlidesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createPresentation**](SlidesApi.md#createpresentationoperation) | **POST** /v1/slides | Create a presentation. |
| [**createSlide**](SlidesApi.md#createslideoperation) | **POST** /v1/slides/{id}/slides | Insert a slide. |
| [**createSlideElement**](SlidesApi.md#createslideelementoperation) | **POST** /v1/slides/{id}/slides/{slideId}/elements | Add a canvas element (text/shape/image) to a slide. |
| [**deletePresentation**](SlidesApi.md#deletepresentation) | **DELETE** /v1/slides/{id} | Delete a presentation. |
| [**deleteSlide**](SlidesApi.md#deleteslide) | **DELETE** /v1/slides/{id}/slides/{slideId} | Delete a slide. |
| [**deleteSlideElement**](SlidesApi.md#deleteslideelement) | **DELETE** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Delete a slide element. |
| [**disablePresentationShare**](SlidesApi.md#disablepresentationshare) | **DELETE** /v1/slides/{id}/share | Disable public sharing. |
| [**enablePresentationShare**](SlidesApi.md#enablepresentationshare) | **POST** /v1/slides/{id}/share | Enable (or update password on) public sharing. |
| [**exportPresentationPdf**](SlidesApi.md#exportpresentationpdf) | **POST** /v1/slides/{id}/export/pdf | Render the presentation as a PDF. |
| [**exportPresentationPptx**](SlidesApi.md#exportpresentationpptx) | **POST** /v1/slides/{id}/export/pptx | Render the presentation as a PowerPoint (.pptx) file. |
| [**getPresentation**](SlidesApi.md#getpresentation) | **GET** /v1/slides/{id} | Fetch one presentation. |
| [**getPresentationShareSettings**](SlidesApi.md#getpresentationsharesettings) | **GET** /v1/slides/{id}/share | Fetch share settings for a presentation. |
| [**getPublicPresentation**](SlidesApi.md#getpublicpresentation) | **GET** /public/slides/{token} | Fetch a publicly shared presentation. |
| [**getSlide**](SlidesApi.md#getslide) | **GET** /v1/slides/{id}/slides/{slideId} | Fetch one slide. |
| [**getSlideElement**](SlidesApi.md#getslideelement) | **GET** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Fetch one slide element. |
| [**listPresentations**](SlidesApi.md#listpresentations) | **GET** /v1/slides | List presentations across connected accounts. |
| [**listSlideElements**](SlidesApi.md#listslideelements) | **GET** /v1/slides/{id}/slides/{slideId}/elements | List the canvas elements on a slide. |
| [**listSlidesInPresentation**](SlidesApi.md#listslidesinpresentation) | **GET** /v1/slides/{id}/slides | List slides in a presentation. |
| [**rotatePresentationShareToken**](SlidesApi.md#rotatepresentationsharetoken) | **POST** /v1/slides/{id}/share/rotate | Rotate the share token, invalidating outstanding URLs. |
| [**updatePresentation**](SlidesApi.md#updatepresentationoperation) | **PATCH** /v1/slides/{id} | Update presentation metadata (partial). |
| [**updateSlide**](SlidesApi.md#updateslideoperation) | **PATCH** /v1/slides/{id}/slides/{slideId} | Update a slide (partial). |
| [**updateSlideElement**](SlidesApi.md#updateslideelementoperation) | **PATCH** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Update a slide element (partial). |



## createPresentation

> Presentation createPresentation(createPresentationRequest, accountId, provider, xWorkspaceID)

Create a presentation.

Creates a new deck under the target account. Target resolution mirrors &#x60;POST /v1/notes&#x60; and &#x60;/v1/sheets&#x60;: body &#x60;accountId&#x60; → &#x60;?accountId&#x3D;&#x60; → body &#x60;provider&#x60; → &#x60;?provider&#x3D;&#x60; → caller\&#39;s single connected account (errors with &#x60;ambiguous_account&#x60; otherwise). The new deck is auto-seeded with one blank slide so the renderer has something to display immediately. 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { CreatePresentationOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // CreatePresentationRequest
    createPresentationRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreatePresentationOperationRequest;

  try {
    const data = await api.createPresentation(body);
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
| **createPresentationRequest** | [CreatePresentationRequest](CreatePresentationRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Presentation created. |  -  |
| **400** | Invalid body, ambiguous account (&#x60;code: ambiguous_account&#x60;), or no slides provider connected (&#x60;code: no_slides_provider&#x60;).  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createSlide

> Slide createSlide(id, createSlideRequest, accountId, xWorkspaceID)

Insert a slide.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { CreateSlideOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // CreateSlideRequest
    createSlideRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateSlideOperationRequest;

  try {
    const data = await api.createSlide(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **createSlideRequest** | [CreateSlideRequest](CreateSlideRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Slide created. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createSlideElement

> SlideElement createSlideElement(id, slideId, createSlideElementRequest, accountId, xWorkspaceID)

Add a canvas element (text/shape/image) to a slide.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { CreateSlideElementOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // CreateSlideElementRequest
    createSlideElementRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateSlideElementOperationRequest;

  try {
    const data = await api.createSlideElement(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **createSlideElementRequest** | [CreateSlideElementRequest](CreateSlideElementRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Element created. |  -  |
| **400** | Invalid body, missing elementType, or missing path id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deletePresentation

> SuccessFlag deletePresentation(id, accountId, xWorkspaceID)

Delete a presentation.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { DeletePresentationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeletePresentationRequest;

  try {
    const data = await api.deletePresentation(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteSlide

> SuccessFlag deleteSlide(id, slideId, accountId, xWorkspaceID)

Delete a slide.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { DeleteSlideRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteSlideRequest;

  try {
    const data = await api.deleteSlide(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteSlideElement

> SuccessFlag deleteSlideElement(id, slideId, elementId, accountId, xWorkspaceID)

Delete a slide element.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { DeleteSlideElementRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // string | Slide-element id.
    elementId: elementId_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteSlideElementRequest;

  try {
    const data = await api.deleteSlideElement(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **elementId** | `string` | Slide-element id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Element not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## disablePresentationShare

> disablePresentationShare(id, accountId, xWorkspaceID)

Disable public sharing.

Owner-only. Subsequent public viewer requests 404.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { DisablePresentationShareRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DisablePresentationShareRequest;

  try {
    const data = await api.disablePresentationShare(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

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
| **204** | Sharing disabled. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## enablePresentationShare

> ShareSettings enablePresentationShare(id, accountId, xWorkspaceID, enableShareRequest)

Enable (or update password on) public sharing.

Owner-only. With &#x60;setPassword: false&#x60; (or empty body), flips the deck public without changing the password. With &#x60;setPassword: true&#x60;, applies &#x60;password&#x60; (empty clears). 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { EnablePresentationShareRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // EnableShareRequest (optional)
    enableShareRequest: ...,
  } satisfies EnablePresentationShareRequest;

  try {
    const data = await api.enablePresentationShare(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **enableShareRequest** | [EnableShareRequest](EnableShareRequest.md) |  | [Optional] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated share settings. |  -  |
| **400** | Password failed strength check. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## exportPresentationPdf

> Blob exportPresentationPdf(id, accountId, xWorkspaceID, storage, filename, exportPDFRequest)

Render the presentation as a PDF.

Proxies to the Spatio export sidecar (Playwright). Two response modes selected via &#x60;?storage&#x3D;&#x60;:    - &#x60;stream&#x60; (default) — response body is the PDF binary     (&#x60;application/pdf&#x60;).   - &#x60;r2&#x60; — uploads the rendered PDF to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns &#x60;503 Service Unavailable&#x60; when the export sidecar is not configured (dev fallback to the client-side exporter). 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { ExportPresentationPdfRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // 'stream' | 'r2' (optional)
    storage: storage_example,
    // string | Sanitized base name for the downloaded PDF. (optional)
    filename: filename_example,
    // ExportPDFRequest (optional)
    exportPDFRequest: ...,
  } satisfies ExportPresentationPdfRequest;

  try {
    const data = await api.exportPresentationPdf(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **storage** | `stream`, `r2` |  | [Optional] [Defaults to `&#39;stream&#39;`] [Enum: stream, r2] |
| **filename** | `string` | Sanitized base name for the downloaded PDF. | [Optional] [Defaults to `undefined`] |
| **exportPDFRequest** | [ExportPDFRequest](ExportPDFRequest.md) |  | [Optional] |

### Return type

**Blob**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/pdf`, `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Either the PDF binary (when &#x60;?storage&#x3D;stream&#x60;) or a JSON envelope with a signed URL (when &#x60;?storage&#x3D;r2&#x60;).  |  -  |
| **400** | Missing id, presentation has no slides, or invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **502** | Export sidecar unreachable or upstream R2 failure. |  -  |
| **503** | Export sidecar not configured. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## exportPresentationPptx

> Blob exportPresentationPptx(id, accountId, xWorkspaceID, storage, filename, exportPDFRequest)

Render the presentation as a PowerPoint (.pptx) file.

Proxies to the Spatio export sidecar (Playwright + pptxgenjs). Each slide is screenshotted at 2× device-pixel ratio and wrapped into a PowerPoint .pptx as a full-bleed image. Visual fidelity is preserved exactly — what renders in Spatio renders identically in PowerPoint, Keynote, Google Slides — at the cost of in-PowerPoint editability of slide content. Users edit slide content back in Spatio (the source of truth), not inside PowerPoint.  Two response modes selected via &#x60;?storage&#x3D;&#x60;:    - &#x60;stream&#x60; (default) — response body is the PPTX binary     (&#x60;application/vnd.openxmlformats-officedocument.presentationml.presentation&#x60;).   - &#x60;r2&#x60; — uploads the rendered PPTX to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns &#x60;503 Service Unavailable&#x60; when the export sidecar is not configured. 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { ExportPresentationPptxRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // 'stream' | 'r2' (optional)
    storage: storage_example,
    // string | Sanitized base name for the downloaded PPTX. (optional)
    filename: filename_example,
    // ExportPDFRequest (optional)
    exportPDFRequest: ...,
  } satisfies ExportPresentationPptxRequest;

  try {
    const data = await api.exportPresentationPptx(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **storage** | `stream`, `r2` |  | [Optional] [Defaults to `&#39;stream&#39;`] [Enum: stream, r2] |
| **filename** | `string` | Sanitized base name for the downloaded PPTX. | [Optional] [Defaults to `undefined`] |
| **exportPDFRequest** | [ExportPDFRequest](ExportPDFRequest.md) |  | [Optional] |

### Return type

**Blob**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/vnd.openxmlformats-officedocument.presentationml.presentation`, `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Either the PPTX binary (when &#x60;?storage&#x3D;stream&#x60;) or a JSON envelope with a signed URL (when &#x60;?storage&#x3D;r2&#x60;).  |  -  |
| **400** | Missing id, presentation has no slides, or invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **502** | Export sidecar unreachable or upstream R2 failure. |  -  |
| **503** | Export sidecar not configured. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPresentation

> Presentation getPresentation(id, accountId, xWorkspaceID)

Fetch one presentation.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { GetPresentationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetPresentationRequest;

  try {
    const data = await api.getPresentation(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The presentation. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPresentationShareSettings

> ShareSettings getPresentationShareSettings(id, accountId, xWorkspaceID)

Fetch share settings for a presentation.

Owner-only. Mirror of &#x60;GET /v1/notes/{id}/share&#x60; — same shape, same fields. Returns the current public-share configuration, including the share token and computed public viewer URL when the deck is currently public. 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { GetPresentationShareSettingsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetPresentationShareSettingsRequest;

  try {
    const data = await api.getPresentationShareSettings(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Current share settings. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPublicPresentation

> { [key: string]: any; } getPublicPresentation(token, password)

Fetch a publicly shared presentation.

Unauthenticated. Mirror of &#x60;GET /public/notes/{token}&#x60;. The share token is the credential. For password-protected decks the password is supplied via &#x60;?password&#x3D;&#x60;; the response distinguishes \&quot;no password supplied\&quot; from \&quot;wrong password\&quot; so the viewer can render the right prompt. Unknown tokens and disabled-share decks both return &#x60;404&#x60; to prevent enumeration. 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { GetPublicPresentationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new SlidesApi();

  const body = {
    // string | Opaque public-share token.
    token: token_example,
    // string | Optional viewer password. (optional)
    password: password_example,
  } satisfies GetPublicPresentationRequest;

  try {
    const data = await api.getPublicPresentation(body);
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
| **token** | `string` | Opaque public-share token. | [Defaults to `undefined`] |
| **password** | `string` | Optional viewer password. | [Optional] [Defaults to `undefined`] |

### Return type

**{ [key: string]: any; }**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Read-only snapshot of the shared presentation. |  -  |
| **400** | Missing token. |  -  |
| **401** | Password-protected deck. &#x60;requiresPassword: true&#x60; always set; &#x60;invalidPassword: true&#x60; only when a password was supplied and rejected.  |  -  |
| **404** | Token unknown or sharing disabled. |  -  |
| **500** | Snapshot rendering failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSlide

> Slide getSlide(id, slideId, accountId, xWorkspaceID)

Fetch one slide.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { GetSlideRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetSlideRequest;

  try {
    const data = await api.getSlide(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The slide. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSlideElement

> SlideElement getSlideElement(id, slideId, elementId, accountId, xWorkspaceID)

Fetch one slide element.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { GetSlideElementRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // string | Slide-element id.
    elementId: elementId_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetSlideElementRequest;

  try {
    const data = await api.getSlideElement(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **elementId** | `string` | Slide-element id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The element. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Element not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPresentations

> PresentationListEnvelope listPresentations(accountId, provider, xWorkspaceID, limit, offset)

List presentations across connected accounts.

Fan-out list. Returns every presentation visible to the caller across every connected slides provider. Pass &#x60;?accountId&#x3D;&#x60; or &#x60;?provider&#x3D;&#x60; to scope to a single source. 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { ListPresentationsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
  } satisfies ListPresentationsRequest;

  try {
    const data = await api.listPresentations(body);
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
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |

### Return type

[**PresentationListEnvelope**](PresentationListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Fan-out envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Resolver or fan-out failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSlideElements

> SlideElementList listSlideElements(id, slideId, accountId, xWorkspaceID)

List the canvas elements on a slide.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { ListSlideElementsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies ListSlideElementsRequest;

  try {
    const data = await api.listSlideElements(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SlideElementList**](SlideElementList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Slide-element list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSlidesInPresentation

> SlideList listSlidesInPresentation(id, accountId, xWorkspaceID)

List slides in a presentation.

Single-account list. Returns slides in the order set by their &#x60;position&#x60; field. 

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { ListSlidesInPresentationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies ListSlidesInPresentationRequest;

  try {
    const data = await api.listSlidesInPresentation(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SlideList**](SlideList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Slide list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## rotatePresentationShareToken

> ShareSettings rotatePresentationShareToken(id, accountId, xWorkspaceID)

Rotate the share token, invalidating outstanding URLs.

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { RotatePresentationShareTokenRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies RotatePresentationShareTokenRequest;

  try {
    const data = await api.rotatePresentationShareToken(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | New share settings (with the new token + URL). |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not the deck owner. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updatePresentation

> Presentation updatePresentation(id, updatePresentationRequest, accountId, xWorkspaceID)

Update presentation metadata (partial).

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { UpdatePresentationOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // UpdatePresentationRequest
    updatePresentationRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdatePresentationOperationRequest;

  try {
    const data = await api.updatePresentation(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **updatePresentationRequest** | [UpdatePresentationRequest](UpdatePresentationRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated presentation. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Presentation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateSlide

> Slide updateSlide(id, slideId, updateSlideRequest, accountId, xWorkspaceID)

Update a slide (partial).

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { UpdateSlideOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // UpdateSlideRequest
    updateSlideRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateSlideOperationRequest;

  try {
    const data = await api.updateSlide(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **updateSlideRequest** | [UpdateSlideRequest](UpdateSlideRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated slide. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Slide not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateSlideElement

> SlideElement updateSlideElement(id, slideId, elementId, updateSlideElementRequest, accountId, xWorkspaceID)

Update a slide element (partial).

### Example

```ts
import {
  Configuration,
  SlidesApi,
} from '@spatio/sdk-ts';
import type { UpdateSlideElementOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SlidesApi(config);

  const body = {
    // string | Presentation id.
    id: id_example,
    // string | Slide id within the presentation.
    slideId: slideId_example,
    // string | Slide-element id.
    elementId: elementId_example,
    // UpdateSlideElementRequest
    updateSlideElementRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateSlideElementOperationRequest;

  try {
    const data = await api.updateSlideElement(body);
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
| **id** | `string` | Presentation id. | [Defaults to `undefined`] |
| **slideId** | `string` | Slide id within the presentation. | [Defaults to `undefined`] |
| **elementId** | `string` | Slide-element id. | [Defaults to `undefined`] |
| **updateSlideElementRequest** | [UpdateSlideElementRequest](UpdateSlideElementRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated element. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Element not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

