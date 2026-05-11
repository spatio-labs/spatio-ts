# SheetsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createSheet**](SheetsApi.md#createsheetoperation) | **POST** /v1/sheets | Create a sheet. |
| [**createSheetRow**](SheetsApi.md#createsheetrow) | **POST** /v1/sheets/{id}/rows | Insert a row. |
| [**deleteSheet**](SheetsApi.md#deletesheet) | **DELETE** /v1/sheets/{id} | Delete a sheet. |
| [**deleteSheetRow**](SheetsApi.md#deletesheetrow) | **DELETE** /v1/sheets/{id}/rows/{rowIndex} | Delete a row. |
| [**getSheet**](SheetsApi.md#getsheet) | **GET** /v1/sheets/{id} | Fetch one sheet. |
| [**listSheetRows**](SheetsApi.md#listsheetrows) | **GET** /v1/sheets/{id}/rows | List rows in a sheet. |
| [**listSheets**](SheetsApi.md#listsheets) | **GET** /v1/sheets | List sheets across connected accounts. |
| [**updateSheet**](SheetsApi.md#updatesheetoperation) | **PATCH** /v1/sheets/{id} | Update a sheet (partial). |
| [**updateSheetCell**](SheetsApi.md#updatesheetcell) | **PATCH** /v1/sheets/{id}/rows/{rowIndex}/cells/{column} | Update a single cell. |
| [**updateSheetRow**](SheetsApi.md#updatesheetrow) | **PATCH** /v1/sheets/{id}/rows/{rowIndex} | Update a row (sparse). |



## createSheet

> Sheet createSheet(createSheetRequest, accountId, provider, xWorkspaceID)

Create a sheet.

Creates a new sheet under the target account. Target resolution mirrors &#x60;POST /v1/notes&#x60;: body &#x60;accountId&#x60; → &#x60;?accountId&#x3D;&#x60; → body &#x60;provider&#x60; → &#x60;?provider&#x3D;&#x60; → caller\&#39;s single connected account (errors with &#x60;ambiguous_account&#x60; if more than one is connected and no selector is supplied). 

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateSheetOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // CreateSheetRequest
    createSheetRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`.  (optional)
    provider: provider_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateSheetOperationRequest;

  try {
    const data = await api.createSheet(body);
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
| **createSheetRequest** | [CreateSheetRequest](CreateSheetRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Sheet**](Sheet.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Sheet created. |  -  |
| **400** | Invalid body, ambiguous account (&#x60;code: ambiguous_account&#x60;), or no sheets provider connected (&#x60;code: no_sheets_provider&#x60;).  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createSheetRow

> Row createSheetRow(id, createRowRequest, accountId, xWorkspaceID)

Insert a row.

Inserts a row at &#x60;index&#x60; (zero-based) or appends to the end when &#x60;index&#x60; is omitted. 

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateSheetRowRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // CreateRowRequest
    createRowRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateSheetRowRequest;

  try {
    const data = await api.createSheetRow(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
| **createRowRequest** | [CreateRowRequest](CreateRowRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Row**](Row.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Row created. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Sheet not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteSheet

> SuccessFlag deleteSheet(id, accountId, xWorkspaceID)

Delete a sheet.

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteSheetRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteSheetRequest;

  try {
    const data = await api.deleteSheet(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
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
| **404** | Sheet not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteSheetRow

> SuccessFlag deleteSheetRow(id, rowIndex, accountId, xWorkspaceID)

Delete a row.

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteSheetRowRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // number | Zero-based row index.
    rowIndex: 56,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteSheetRowRequest;

  try {
    const data = await api.deleteSheetRow(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
| **rowIndex** | `number` | Zero-based row index. | [Defaults to `undefined`] |
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
| **400** | Missing id or invalid row index. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Sheet or row not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSheet

> Sheet getSheet(id, accountId, xWorkspaceID)

Fetch one sheet.

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { GetSheetRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetSheetRequest;

  try {
    const data = await api.getSheet(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Sheet**](Sheet.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The sheet. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Sheet not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSheetRows

> RowList listSheetRows(id, accountId, xWorkspaceID, limit, offset)

List rows in a sheet.

Single-account row list. Unlike &#x60;GET /v1/sheets&#x60;, row listing always targets the one account that owns the sheet, so the response is a plain &#x60;{ rows, total }&#x60; rather than a fan-out envelope. 

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { ListSheetRowsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
  } satisfies ListSheetRowsRequest;

  try {
    const data = await api.listSheetRows(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `100`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |

### Return type

[**RowList**](RowList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Row list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Sheet not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSheets

> SheetListEnvelope listSheets(accountId, provider, xWorkspaceID, limit, offset)

List sheets across connected accounts.

Fan-out list. Returns every sheet visible to the caller across every connected sheets provider, paginated by &#x60;limit&#x60; / &#x60;offset&#x60;. Pass &#x60;?accountId&#x3D;&#x60; or &#x60;?provider&#x3D;&#x60; to scope to a single source. 

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { ListSheetsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

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
  } satisfies ListSheetsRequest;

  try {
    const data = await api.listSheets(body);
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

[**SheetListEnvelope**](SheetListEnvelope.md)

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


## updateSheet

> Sheet updateSheet(id, updateSheetRequest, accountId, xWorkspaceID)

Update a sheet (partial).

Partial update of sheet metadata. The renderer also calls this via &#x60;PUT /v1/sheets/{id}&#x60; for autosave parity; both verbs invoke the same handler. Per-cell and per-row mutations live on their dedicated endpoints, not here. 

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateSheetOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // UpdateSheetRequest
    updateSheetRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateSheetOperationRequest;

  try {
    const data = await api.updateSheet(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
| **updateSheetRequest** | [UpdateSheetRequest](UpdateSheetRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Sheet**](Sheet.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated sheet. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Sheet not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateSheetCell

> Cell updateSheetCell(id, rowIndex, column, updateCellRequest, accountId, xWorkspaceID)

Update a single cell.

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateSheetCellRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // number | Zero-based row index.
    rowIndex: 56,
    // string | Column identifier. Provider-specific — usually a letter (`A`, `AB`) for spreadsheet providers or a column key string for structured providers. 
    column: column_example,
    // UpdateCellRequest
    updateCellRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateSheetCellRequest;

  try {
    const data = await api.updateSheetCell(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
| **rowIndex** | `number` | Zero-based row index. | [Defaults to `undefined`] |
| **column** | `string` | Column identifier. Provider-specific — usually a letter (&#x60;A&#x60;, &#x60;AB&#x60;) for spreadsheet providers or a column key string for structured providers.  | [Defaults to `undefined`] |
| **updateCellRequest** | [UpdateCellRequest](UpdateCellRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Cell**](Cell.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell. |  -  |
| **400** | Invalid body, missing id, invalid row index, or missing column.  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Sheet, row, or cell not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateSheetRow

> Row updateSheetRow(id, rowIndex, updateRowRequest, accountId, xWorkspaceID)

Update a row (sparse).

Sparse update — keys present in &#x60;cells&#x60; overwrite that column; keys absent are preserved. 

### Example

```ts
import {
  Configuration,
  SheetsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateSheetRowRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SheetsApi(config);

  const body = {
    // string | Sheet id.
    id: id_example,
    // number | Zero-based row index.
    rowIndex: 56,
    // UpdateRowRequest
    updateRowRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateSheetRowRequest;

  try {
    const data = await api.updateSheetRow(body);
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
| **id** | `string` | Sheet id. | [Defaults to `undefined`] |
| **rowIndex** | `number` | Zero-based row index. | [Defaults to `undefined`] |
| **updateRowRequest** | [UpdateRowRequest](UpdateRowRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**Row**](Row.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated row. |  -  |
| **400** | Invalid body, missing id, or invalid row index. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Sheet or row not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

