# FilesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**bulkDeleteFiles**](FilesApi.md#bulkdeletefilesoperation) | **POST** /v1/files/delete | Delete multiple files in one call. |
| [**bulkMoveFiles**](FilesApi.md#bulkmovefilesoperation) | **POST** /v1/files/move | Move multiple files to a target folder. |
| [**commitChunkedUpload**](FilesApi.md#commitchunkeduploadoperation) | **POST** /v1/files/upload/chunked/commit | Finalize a chunked-upload session and create the file row. |
| [**createFileFolder**](FilesApi.md#createfilefolder) | **POST** /v1/files/folders | Create a folder. |
| [**deleteFile**](FilesApi.md#deletefile) | **DELETE** /v1/files/{id} | Delete a file. |
| [**extractFileText**](FilesApi.md#extractfiletext) | **GET** /v1/files/{id}/extract-text | Extract text content from a PDF (or other supported file). |
| [**getChunkedFileManifest**](FilesApi.md#getchunkedfilemanifest) | **GET** /v1/files/{id}/manifest | Fetch the block manifest for a chunked-uploaded file. |
| [**getFile**](FilesApi.md#getfile) | **GET** /v1/files/{id} | Fetch one file\&#39;s metadata. |
| [**getFileDownloadUrl**](FilesApi.md#getfiledownloadurl) | **GET** /v1/files/{id}/download | Mint a fresh signed download URL. |
| [**initChunkedUpload**](FilesApi.md#initchunkeduploadoperation) | **POST** /v1/files/upload/chunked/init | Begin a content-addressed chunked upload session. |
| [**listFileFolders**](FilesApi.md#listfilefolders) | **GET** /v1/files/folders | List folders across connected file providers. |
| [**listFiles**](FilesApi.md#listfiles) | **GET** /v1/files | List files across connected file providers. |
| [**listFilesAndFolders**](FilesApi.md#listfilesandfolders) | **GET** /v1/files/list | Aggregate list of files + folders for renderer file-browser views. |
| [**moveFile**](FilesApi.md#movefileoperation) | **POST** /v1/files/{id}/move | Move a single file to a target folder. |
| [**searchFiles**](FilesApi.md#searchfiles) | **GET** /v1/files/search | Substring-match search across the caller\&#39;s files. |
| [**updateFile**](FilesApi.md#updatefileoperation) | **PATCH** /v1/files/{id} | Update a file\&#39;s metadata (name, folder, custom fields). |
| [**uploadChunkedBlock**](FilesApi.md#uploadchunkedblock) | **POST** /v1/files/upload/chunked/blocks | Upload one block for an open chunked-upload session. |
| [**uploadFile**](FilesApi.md#uploadfile) | **POST** /v1/files/upload | Upload a file via multipart form. |
| [**uploadFileBase64**](FilesApi.md#uploadfilebase64operation) | **POST** /v1/files/upload/base64 | Upload a file via JSON with base64-encoded content. |
| [**workspaceCommitChunkedUpload**](FilesApi.md#workspacecommitchunkedupload) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/chunked/commit | Workspace-scoped chunked-upload commit (RBAC-protected). |
| [**workspaceCreateFileFolder**](FilesApi.md#workspacecreatefilefolder) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/folders | Workspace-scoped create-folder (RBAC-protected). |
| [**workspaceDeleteFile**](FilesApi.md#workspacedeletefile) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/files/{id} | Workspace-scoped delete-file. |
| [**workspaceGetFile**](FilesApi.md#workspacegetfile) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/{id} | Workspace-scoped get-file. |
| [**workspaceGetFileDownload**](FilesApi.md#workspacegetfiledownload) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/{id}/download | Workspace-scoped signed-download URL. |
| [**workspaceGetFileManifest**](FilesApi.md#workspacegetfilemanifest) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/{id}/manifest | Workspace-scoped chunked-file manifest. |
| [**workspaceInitChunkedUpload**](FilesApi.md#workspaceinitchunkedupload) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/chunked/init | Workspace-scoped chunked-upload init (RBAC-protected). |
| [**workspaceListFileFolders**](FilesApi.md#workspacelistfilefolders) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/folders | Workspace-scoped list-folders (RBAC-protected). |
| [**workspaceListFiles**](FilesApi.md#workspacelistfiles) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files | Workspace-scoped list-files (RBAC-protected). |
| [**workspaceMoveFile**](FilesApi.md#workspacemovefile) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/{id}/move | Workspace-scoped move-file. |
| [**workspaceUpdateFile**](FilesApi.md#workspaceupdatefile) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/files/{id} | Workspace-scoped update-file. |
| [**workspaceUploadChunkedBlock**](FilesApi.md#workspaceuploadchunkedblock) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/chunked/blocks | Workspace-scoped chunked-upload block (RBAC-protected). |
| [**workspaceUploadFile**](FilesApi.md#workspaceuploadfile) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload | Workspace-scoped multipart upload (RBAC-protected). |
| [**workspaceUploadFileBase64**](FilesApi.md#workspaceuploadfilebase64) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/base64 | Workspace-scoped base64 upload (RBAC-protected). |



## bulkDeleteFiles

> BulkFilesResponse bulkDeleteFiles(bulkDeleteFilesRequest)

Delete multiple files in one call.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { BulkDeleteFilesOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // BulkDeleteFilesRequest
    bulkDeleteFilesRequest: ...,
  } satisfies BulkDeleteFilesOperationRequest;

  try {
    const data = await api.bulkDeleteFiles(body);
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
| **bulkDeleteFilesRequest** | [BulkDeleteFilesRequest](BulkDeleteFilesRequest.md) |  | |

### Return type

[**BulkFilesResponse**](BulkFilesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Partial-success envelope. |  -  |
| **400** | Body missing or empty. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## bulkMoveFiles

> BulkFilesResponse bulkMoveFiles(bulkMoveFilesRequest)

Move multiple files to a target folder.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { BulkMoveFilesOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // BulkMoveFilesRequest
    bulkMoveFilesRequest: ...,
  } satisfies BulkMoveFilesOperationRequest;

  try {
    const data = await api.bulkMoveFiles(body);
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
| **bulkMoveFilesRequest** | [BulkMoveFilesRequest](BulkMoveFilesRequest.md) |  | |

### Return type

[**BulkFilesResponse**](BulkFilesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Partial-success envelope. |  -  |
| **400** | Body missing or empty. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## commitChunkedUpload

> CommitChunkedUploadResponse commitChunkedUpload(commitChunkedUploadRequest)

Finalize a chunked-upload session and create the file row.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { CommitChunkedUploadOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // CommitChunkedUploadRequest
    commitChunkedUploadRequest: ...,
  } satisfies CommitChunkedUploadOperationRequest;

  try {
    const data = await api.commitChunkedUpload(body);
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
| **commitChunkedUploadRequest** | [CommitChunkedUploadRequest](CommitChunkedUploadRequest.md) |  | |

### Return type

[**CommitChunkedUploadResponse**](CommitChunkedUploadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | File created. |  -  |
| **400** | Unknown session or missing blocks. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createFileFolder

> Folder createFileFolder(createFolderRequest, accountId, provider, xWorkspaceID)

Create a folder.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { CreateFileFolderRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // CreateFolderRequest
    createFolderRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateFileFolderRequest;

  try {
    const data = await api.createFileFolder(body);
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
| **createFolderRequest** | [CreateFolderRequest](CreateFolderRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Folder**](Folder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Folder created. |  -  |
| **400** | Invalid body or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteFile

> deleteFile(id, accountId, xWorkspaceID)

Delete a file.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { DeleteFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | File id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteFileRequest;

  try {
    const data = await api.deleteFile(body);
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
| **id** | `string` | File id. | [Defaults to `undefined`] |
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
| **204** | File deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | File not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## extractFileText

> ExtractTextResult extractFileText(id, accountId, xWorkspaceID, pageStart, pageEnd, maxChars)

Extract text content from a PDF (or other supported file).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { ExtractFileTextRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | File id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // number (optional)
    pageStart: 56,
    // number (optional)
    pageEnd: 56,
    // number | Truncation limit; sets `truncated: true` when hit. (optional)
    maxChars: 56,
  } satisfies ExtractFileTextRequest;

  try {
    const data = await api.extractFileText(body);
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
| **id** | `string` | File id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **pageStart** | `number` |  | [Optional] [Defaults to `undefined`] |
| **pageEnd** | `number` |  | [Optional] [Defaults to `undefined`] |
| **maxChars** | `number` | Truncation limit; sets &#x60;truncated: true&#x60; when hit. | [Optional] [Defaults to `undefined`] |

### Return type

[**ExtractTextResult**](ExtractTextResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Extracted text. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | File not found. |  -  |
| **422** | File type isn\&#39;t supported for extraction. &#x60;code: extraction_unsupported&#x60; is reserved.  |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getChunkedFileManifest

> ChunkedFileManifest getChunkedFileManifest(id, accountId, xWorkspaceID)

Fetch the block manifest for a chunked-uploaded file.

Only meaningful for files uploaded via &#x60;upload/chunked/_*&#x60;. Files uploaded via &#x60;upload&#x60; or &#x60;upload/base64&#x60; return &#x60;404&#x60;. 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { GetChunkedFileManifestRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | File id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetChunkedFileManifestRequest;

  try {
    const data = await api.getChunkedFileManifest(body);
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
| **id** | `string` | File id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**ChunkedFileManifest**](ChunkedFileManifest.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Block manifest. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | File not found or not chunked-uploaded. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getFile

> SpatioFile getFile(id, accountId, xWorkspaceID)

Fetch one file\&#39;s metadata.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { GetFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | File id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetFileRequest;

  try {
    const data = await api.getFile(body);
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
| **id** | `string` | File id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The file. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | File not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getFileDownloadUrl

> DownloadFileResponse getFileDownloadUrl(id, accountId, xWorkspaceID)

Mint a fresh signed download URL.

Returns a JSON envelope with a pre-signed URL pointing at the backing storage. Clients follow the URL — the platform does not stream bytes through itself. 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { GetFileDownloadUrlRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | File id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetFileDownloadUrlRequest;

  try {
    const data = await api.getFileDownloadUrl(body);
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
| **id** | `string` | File id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**DownloadFileResponse**](DownloadFileResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Download envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | File not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## initChunkedUpload

> InitChunkedUploadResponse initChunkedUpload(initChunkedUploadRequest)

Begin a content-addressed chunked upload session.

Client computes per-block hashes ahead of time and submits the list. The server replies with which blocks need uploading vs. already-on-server (deduplicated). Subsequent calls upload the missing blocks via &#x60;uploadChunkedBlock&#x60;, then &#x60;commit&#x60;. 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { InitChunkedUploadOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // InitChunkedUploadRequest
    initChunkedUploadRequest: ...,
  } satisfies InitChunkedUploadOperationRequest;

  try {
    const data = await api.initChunkedUpload(body);
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
| **initChunkedUploadRequest** | [InitChunkedUploadRequest](InitChunkedUploadRequest.md) |  | |

### Return type

[**InitChunkedUploadResponse**](InitChunkedUploadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Session opened. |  -  |
| **400** | Invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listFileFolders

> FolderListEnvelope listFileFolders(accountId, provider, xWorkspaceID, parentId, workspaceId, organizationId, limit, offset)

List folders across connected file providers.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { ListFileFoldersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // string | Filter to children of this folder. Omit for root. (optional)
    parentId: parentId_example,
    // string (optional)
    workspaceId: workspaceId_example,
    // string (optional)
    organizationId: organizationId_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
  } satisfies ListFileFoldersRequest;

  try {
    const data = await api.listFileFolders(body);
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
| **parentId** | `string` | Filter to children of this folder. Omit for root. | [Optional] [Defaults to `undefined`] |
| **workspaceId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **organizationId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |

### Return type

[**FolderListEnvelope**](FolderListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Fan-out folder list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listFiles

> FileListEnvelope listFiles(accountId, provider, xWorkspaceID, folderId, workspaceId, organizationId, limit, offset, sortBy, sortOrder)

List files across connected file providers.

Fan-out list. Returns files from every connected file provider unless filtered by &#x60;?accountId&#x3D;&#x60; or &#x60;?provider&#x3D;&#x60;. Folder contents are scoped via &#x60;?folderId&#x3D;&#x60;; omit for account root. 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { ListFilesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // string | Filter to one folder. Omit for the account root. (optional)
    folderId: folderId_example,
    // string (optional)
    workspaceId: workspaceId_example,
    // string (optional)
    organizationId: organizationId_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
    // string | Provider-dependent. Common values: `created_at`, `name`, `size`. (optional)
    sortBy: sortBy_example,
    // 'ASC' | 'DESC' (optional)
    sortOrder: sortOrder_example,
  } satisfies ListFilesRequest;

  try {
    const data = await api.listFiles(body);
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
| **folderId** | `string` | Filter to one folder. Omit for the account root. | [Optional] [Defaults to `undefined`] |
| **workspaceId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **organizationId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |
| **sortBy** | `string` | Provider-dependent. Common values: &#x60;created_at&#x60;, &#x60;name&#x60;, &#x60;size&#x60;. | [Optional] [Defaults to `&#39;created_at&#39;`] |
| **sortOrder** | `ASC`, `DESC` |  | [Optional] [Defaults to `&#39;DESC&#39;`] [Enum: ASC, DESC] |

### Return type

[**FileListEnvelope**](FileListEnvelope.md)

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


## listFilesAndFolders

> FilesAndFoldersResponse listFilesAndFolders(accountId, provider, folderId, workspaceId, organizationId, limit, offset, sortBy, sortOrder)

Aggregate list of files + folders for renderer file-browser views.

Calls &#x60;listFiles&#x60; and &#x60;listFileFolders&#x60; in parallel and merges the results. Saves a round-trip when the UI shows both side-by-side. 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { ListFilesAndFoldersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Filter to one folder. Omit for the account root. (optional)
    folderId: folderId_example,
    // string (optional)
    workspaceId: workspaceId_example,
    // string (optional)
    organizationId: organizationId_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
    // string (optional)
    sortBy: sortBy_example,
    // string (optional)
    sortOrder: sortOrder_example,
  } satisfies ListFilesAndFoldersRequest;

  try {
    const data = await api.listFilesAndFolders(body);
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
| **folderId** | `string` | Filter to one folder. Omit for the account root. | [Optional] [Defaults to `undefined`] |
| **workspaceId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **organizationId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |
| **sortBy** | `string` |  | [Optional] [Defaults to `undefined`] |
| **sortOrder** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**FilesAndFoldersResponse**](FilesAndFoldersResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Aggregated &#x60;{files, folders, accounts}&#x60; envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## moveFile

> MoveFileResponse moveFile(id, moveFileRequest, accountId, xWorkspaceID)

Move a single file to a target folder.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { MoveFileOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | File id.
    id: id_example,
    // MoveFileRequest
    moveFileRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies MoveFileOperationRequest;

  try {
    const data = await api.moveFile(body);
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
| **id** | `string` | File id. | [Defaults to `undefined`] |
| **moveFileRequest** | [MoveFileRequest](MoveFileRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**MoveFileResponse**](MoveFileResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Move ack. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | File not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchFiles

> SearchFilesResponse searchFiles(query, accountId, provider, folderId, workspaceId, organizationId, limit, offset)

Substring-match search across the caller\&#39;s files.

In-memory search — the platform lists up to ~500 files and filters locally on &#x60;name&#x60; (case-insensitive substring). Not suitable for global search across very large file libraries. 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { SearchFilesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    query: query_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Filter to one folder. Omit for the account root. (optional)
    folderId: folderId_example,
    // string (optional)
    workspaceId: workspaceId_example,
    // string (optional)
    organizationId: organizationId_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
  } satisfies SearchFilesRequest;

  try {
    const data = await api.searchFiles(body);
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
| **query** | `string` |  | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [Optional] [Defaults to `undefined`] |
| **folderId** | `string` | Filter to one folder. Omit for the account root. | [Optional] [Defaults to `undefined`] |
| **workspaceId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **organizationId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |

### Return type

[**SearchFilesResponse**](SearchFilesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Filtered file list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateFile

> SpatioFile updateFile(id, updateFileRequest, accountId, xWorkspaceID)

Update a file\&#39;s metadata (name, folder, custom fields).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { UpdateFileOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string | File id.
    id: id_example,
    // UpdateFileRequest
    updateFileRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateFileOperationRequest;

  try {
    const data = await api.updateFile(body);
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
| **id** | `string` | File id. | [Defaults to `undefined`] |
| **updateFileRequest** | [UpdateFileRequest](UpdateFileRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated file. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | File not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## uploadChunkedBlock

> UploadChunkedBlockResponse uploadChunkedBlock(sessionId, blockHash, block, blockIndex)

Upload one block for an open chunked-upload session.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { UploadChunkedBlockRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    sessionId: sessionId_example,
    // string
    blockHash: blockHash_example,
    // Blob
    block: BINARY_DATA_HERE,
    // number (optional)
    blockIndex: 56,
  } satisfies UploadChunkedBlockRequest;

  try {
    const data = await api.uploadChunkedBlock(body);
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
| **sessionId** | `string` |  | [Defaults to `undefined`] |
| **blockHash** | `string` |  | [Defaults to `undefined`] |
| **block** | `Blob` |  | [Defaults to `undefined`] |
| **blockIndex** | `number` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**UploadChunkedBlockResponse**](UploadChunkedBlockResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Block accepted. |  -  |
| **400** | Missing fields, unknown session, or hash mismatch. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## uploadFile

> SpatioFile uploadFile(file, folderId, workspaceId, organizationId, accountId)

Upload a file via multipart form.

Multipart upload. Form field &#x60;file&#x60; carries the binary; auxiliary form fields scope the upload (&#x60;folderId&#x60;, &#x60;workspaceId&#x60;, &#x60;organizationId&#x60;, &#x60;accountId&#x60;). Max body size is currently 100 MB. 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { UploadFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // Blob | File bytes (multipart form field name `file`).
    file: BINARY_DATA_HERE,
    // string (optional)
    folderId: folderId_example,
    // string (optional)
    workspaceId: workspaceId_example,
    // string (optional)
    organizationId: organizationId_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies UploadFileRequest;

  try {
    const data = await api.uploadFile(body);
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
| **file** | `Blob` | File bytes (multipart form field name &#x60;file&#x60;). | [Defaults to `undefined`] |
| **folderId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **workspaceId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **organizationId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | File created. |  -  |
| **400** | Multipart parse error, ambiguous account, or no file provider connected.  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **402** | Storage quota exceeded. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## uploadFileBase64

> SpatioFile uploadFileBase64(uploadFileBase64Request)

Upload a file via JSON with base64-encoded content.

Equivalent to &#x60;uploadFile&#x60; for clients that can\&#39;t post multipart bodies (e.g. browser fetch with strict CSP). 

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { UploadFileBase64OperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // UploadFileBase64Request
    uploadFileBase64Request: ...,
  } satisfies UploadFileBase64OperationRequest;

  try {
    const data = await api.uploadFileBase64(body);
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
| **uploadFileBase64Request** | [UploadFileBase64Request](UploadFileBase64Request.md) |  | |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | File created. |  -  |
| **400** | Invalid body, ambiguous account, or no provider. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **402** | Storage quota exceeded. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCommitChunkedUpload

> { [key: string]: any; } workspaceCommitChunkedUpload(org, workspace, requestBody)

Workspace-scoped chunked-upload commit (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCommitChunkedUploadRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCommitChunkedUploadRequest;

  try {
    const data = await api.workspaceCommitChunkedUpload(body);
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
| **200** | Committed |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateFileFolder

> { [key: string]: any; } workspaceCreateFileFolder(org, workspace, requestBody)

Workspace-scoped create-folder (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCreateFileFolderRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateFileFolderRequest;

  try {
    const data = await api.workspaceCreateFileFolder(body);
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


## workspaceDeleteFile

> workspaceDeleteFile(org, workspace, id)

Workspace-scoped delete-file.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceDeleteFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceDeleteFileRequest;

  try {
    const data = await api.workspaceDeleteFile(body);
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
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetFile

> { [key: string]: any; } workspaceGetFile(org, workspace, id)

Workspace-scoped get-file.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetFileRequest;

  try {
    const data = await api.workspaceGetFile(body);
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | File |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetFileDownload

> { [key: string]: any; } workspaceGetFileDownload(org, workspace, id)

Workspace-scoped signed-download URL.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetFileDownloadRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetFileDownloadRequest;

  try {
    const data = await api.workspaceGetFileDownload(body);
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Download URL envelope |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetFileManifest

> { [key: string]: any; } workspaceGetFileManifest(org, workspace, id)

Workspace-scoped chunked-file manifest.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetFileManifestRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetFileManifestRequest;

  try {
    const data = await api.workspaceGetFileManifest(body);
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Manifest |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceInitChunkedUpload

> { [key: string]: any; } workspaceInitChunkedUpload(org, workspace, requestBody)

Workspace-scoped chunked-upload init (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceInitChunkedUploadRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceInitChunkedUploadRequest;

  try {
    const data = await api.workspaceInitChunkedUpload(body);
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
| **200** | Init result |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListFileFolders

> { [key: string]: any; } workspaceListFileFolders(org, workspace)

Workspace-scoped list-folders (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListFileFoldersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListFileFoldersRequest;

  try {
    const data = await api.workspaceListFileFolders(body);
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
| **200** | Folder envelope |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListFiles

> { [key: string]: any; } workspaceListFiles(org, workspace)

Workspace-scoped list-files (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListFilesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListFilesRequest;

  try {
    const data = await api.workspaceListFiles(body);
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
| **200** | File envelope |  -  |
| **401** | Caller is not authenticated |  -  |
| **403** | Caller lacks workspace files:read |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceMoveFile

> { [key: string]: any; } workspaceMoveFile(org, workspace, id, requestBody)

Workspace-scoped move-file.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceMoveFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceMoveFileRequest;

  try {
    const data = await api.workspaceMoveFile(body);
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
| **200** | Moved |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUpdateFile

> { [key: string]: any; } workspaceUpdateFile(org, workspace, id, requestBody)

Workspace-scoped update-file.

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceUpdateFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateFileRequest;

  try {
    const data = await api.workspaceUpdateFile(body);
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


## workspaceUploadChunkedBlock

> { [key: string]: any; } workspaceUploadChunkedBlock(org, workspace, body)

Workspace-scoped chunked-upload block (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceUploadChunkedBlockRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // Blob
    body: BINARY_DATA_HERE,
  } satisfies WorkspaceUploadChunkedBlockRequest;

  try {
    const data = await api.workspaceUploadChunkedBlock(body);
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
| **body** | `Blob` |  | |

### Return type

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/octet-stream`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Block uploaded |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUploadFile

> { [key: string]: any; } workspaceUploadFile(org, workspace, file)

Workspace-scoped multipart upload (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceUploadFileRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // Blob (optional)
    file: BINARY_DATA_HERE,
  } satisfies WorkspaceUploadFileRequest;

  try {
    const data = await api.workspaceUploadFile(body);
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
| **file** | `Blob` |  | [Optional] [Defaults to `undefined`] |

### Return type

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Uploaded |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUploadFileBase64

> { [key: string]: any; } workspaceUploadFileBase64(org, workspace, requestBody)

Workspace-scoped base64 upload (RBAC-protected).

### Example

```ts
import {
  Configuration,
  FilesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceUploadFileBase64Request } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FilesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUploadFileBase64Request;

  try {
    const data = await api.workspaceUploadFileBase64(body);
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
| **201** | Uploaded |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

