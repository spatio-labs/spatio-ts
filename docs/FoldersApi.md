# FoldersApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createEmailFolder**](FoldersApi.md#createemailfolderoperation) | **POST** /v1/folders | Create an email folder. |
| [**deleteEmailFolder**](FoldersApi.md#deleteemailfolder) | **DELETE** /v1/folders/{id} | Delete an email folder. |
| [**listEmailFolders**](FoldersApi.md#listemailfolders) | **GET** /v1/folders | List the caller\&#39;s email folders. |
| [**listFolderEmails**](FoldersApi.md#listfolderemails) | **GET** /v1/folders/{id}/emails | List emails inside a folder. |
| [**moveEmailsToFolder**](FoldersApi.md#moveemailstofolder) | **POST** /v1/folders/{id}/emails | Move emails into a folder. |
| [**updateEmailFolder**](FoldersApi.md#updateemailfolderoperation) | **PUT** /v1/folders/{id} | Update an email folder. |



## createEmailFolder

> EmailFolder createEmailFolder(createEmailFolderRequest)

Create an email folder.

### Example

```ts
import {
  Configuration,
  FoldersApi,
} from '@spatio-labs/spatio-ts';
import type { CreateEmailFolderOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FoldersApi(config);

  const body = {
    // CreateEmailFolderRequest
    createEmailFolderRequest: ...,
  } satisfies CreateEmailFolderOperationRequest;

  try {
    const data = await api.createEmailFolder(body);
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
| **createEmailFolderRequest** | [CreateEmailFolderRequest](CreateEmailFolderRequest.md) |  | |

### Return type

[**EmailFolder**](EmailFolder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteEmailFolder

> deleteEmailFolder(id)

Delete an email folder.

### Example

```ts
import {
  Configuration,
  FoldersApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteEmailFolderRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FoldersApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteEmailFolderRequest;

  try {
    const data = await api.deleteEmailFolder(body);
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
| **204** | Deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listEmailFolders

> EmailFolderListResponse listEmailFolders()

List the caller\&#39;s email folders.

### Example

```ts
import {
  Configuration,
  FoldersApi,
} from '@spatio-labs/spatio-ts';
import type { ListEmailFoldersRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FoldersApi(config);

  try {
    const data = await api.listEmailFolders();
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

[**EmailFolderListResponse**](EmailFolderListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Folder envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listFolderEmails

> { [key: string]: any; } listFolderEmails(id)

List emails inside a folder.

### Example

```ts
import {
  Configuration,
  FoldersApi,
} from '@spatio-labs/spatio-ts';
import type { ListFolderEmailsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FoldersApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies ListFolderEmailsRequest;

  try {
    const data = await api.listFolderEmails(body);
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Email list (open shape — provider-tied). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## moveEmailsToFolder

> { [key: string]: any; } moveEmailsToFolder(id, moveEmailsRequest)

Move emails into a folder.

### Example

```ts
import {
  Configuration,
  FoldersApi,
} from '@spatio-labs/spatio-ts';
import type { MoveEmailsToFolderRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FoldersApi(config);

  const body = {
    // string
    id: id_example,
    // MoveEmailsRequest
    moveEmailsRequest: ...,
  } satisfies MoveEmailsToFolderRequest;

  try {
    const data = await api.moveEmailsToFolder(body);
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
| **moveEmailsRequest** | [MoveEmailsRequest](MoveEmailsRequest.md) |  | |

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


## updateEmailFolder

> EmailFolder updateEmailFolder(id, updateEmailFolderRequest)

Update an email folder.

### Example

```ts
import {
  Configuration,
  FoldersApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateEmailFolderOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FoldersApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateEmailFolderRequest
    updateEmailFolderRequest: ...,
  } satisfies UpdateEmailFolderOperationRequest;

  try {
    const data = await api.updateEmailFolder(body);
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
| **updateEmailFolderRequest** | [UpdateEmailFolderRequest](UpdateEmailFolderRequest.md) |  | |

### Return type

[**EmailFolder**](EmailFolder.md)

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

