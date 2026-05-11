# RecordsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createRecord**](RecordsApi.md#createrecordoperation) | **POST** /v1/records | Create a record. |
| [**createRecordType**](RecordsApi.md#createrecordtypeoperation) | **POST** /v1/records/types | Create a record type (org-scoped). |
| [**deleteRecord**](RecordsApi.md#deleterecord) | **DELETE** /v1/records/{id} | Delete a record. |
| [**getRecord**](RecordsApi.md#getrecord) | **GET** /v1/records/{id} | Fetch a record. |
| [**listRecordTypes**](RecordsApi.md#listrecordtypes) | **GET** /v1/records/types | List record types for an organization. |
| [**listRecords**](RecordsApi.md#listrecords) | **GET** /v1/records | List records for an organization. &#x60;organization_id&#x60; query param is required (handler returns 400 otherwise).  |
| [**updateRecord**](RecordsApi.md#updaterecordoperation) | **PATCH** /v1/records/{id} | Update a record. |
| [**updateRecordType**](RecordsApi.md#updaterecordtypeoperation) | **PATCH** /v1/records/types/{id} | Update a record type. |



## createRecord

> ModelRecord createRecord(createRecordRequest)

Create a record.

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateRecordOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // CreateRecordRequest
    createRecordRequest: ...,
  } satisfies CreateRecordOperationRequest;

  try {
    const data = await api.createRecord(body);
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
| **createRecordRequest** | [CreateRecordRequest](CreateRecordRequest.md) |  | |

### Return type

[**ModelRecord**](ModelRecord.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created record. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createRecordType

> RecordType createRecordType(createRecordTypeRequest)

Create a record type (org-scoped).

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateRecordTypeOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // CreateRecordTypeRequest
    createRecordTypeRequest: ...,
  } satisfies CreateRecordTypeOperationRequest;

  try {
    const data = await api.createRecordType(body);
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
| **createRecordTypeRequest** | [CreateRecordTypeRequest](CreateRecordTypeRequest.md) |  | |

### Return type

[**RecordType**](RecordType.md)

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


## deleteRecord

> deleteRecord(id)

Delete a record.

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteRecordRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteRecordRequest;

  try {
    const data = await api.deleteRecord(body);
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


## getRecord

> ModelRecord getRecord(id)

Fetch a record.

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { GetRecordRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetRecordRequest;

  try {
    const data = await api.getRecord(body);
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

[**ModelRecord**](ModelRecord.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Record. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRecordTypes

> RecordTypeListResponse listRecordTypes(organizationId)

List record types for an organization.

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { ListRecordTypesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // string
    organizationId: organizationId_example,
  } satisfies ListRecordTypesRequest;

  try {
    const data = await api.listRecordTypes(body);
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
| **organizationId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**RecordTypeListResponse**](RecordTypeListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Record-type envelope. |  -  |
| **400** | Missing organization_id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRecords

> RecordListResponse listRecords(organizationId, recordTypeId, limit)

List records for an organization. &#x60;organization_id&#x60; query param is required (handler returns 400 otherwise). 

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { ListRecordsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // string
    organizationId: organizationId_example,
    // string (optional)
    recordTypeId: recordTypeId_example,
    // number (optional)
    limit: 56,
  } satisfies ListRecordsRequest;

  try {
    const data = await api.listRecords(body);
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
| **organizationId** | `string` |  | [Defaults to `undefined`] |
| **recordTypeId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**RecordListResponse**](RecordListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Record envelope. |  -  |
| **400** | Missing organization_id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateRecord

> ModelRecord updateRecord(id, updateRecordRequest)

Update a record.

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateRecordOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateRecordRequest
    updateRecordRequest: ...,
  } satisfies UpdateRecordOperationRequest;

  try {
    const data = await api.updateRecord(body);
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
| **updateRecordRequest** | [UpdateRecordRequest](UpdateRecordRequest.md) |  | |

### Return type

[**ModelRecord**](ModelRecord.md)

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


## updateRecordType

> RecordType updateRecordType(id, updateRecordTypeRequest)

Update a record type.

### Example

```ts
import {
  Configuration,
  RecordsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateRecordTypeOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecordsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateRecordTypeRequest
    updateRecordTypeRequest: ...,
  } satisfies UpdateRecordTypeOperationRequest;

  try {
    const data = await api.updateRecordType(body);
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
| **updateRecordTypeRequest** | [UpdateRecordTypeRequest](UpdateRecordTypeRequest.md) |  | |

### Return type

[**RecordType**](RecordType.md)

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

