# ContactsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**assignContactCategory**](ContactsApi.md#assigncontactcategoryoperation) | **POST** /v1/contacts/{id}/categories | Assign a category to a contact. |
| [**createContact**](ContactsApi.md#createcontactoperation) | **POST** /v1/contacts | Create a contact. |
| [**createContactCategory**](ContactsApi.md#createcontactcategoryoperation) | **POST** /v1/contacts/categories | Create a contact category. |
| [**deleteContact**](ContactsApi.md#deletecontact) | **DELETE** /v1/contacts/{id} | Delete a contact. |
| [**deleteContactCategory**](ContactsApi.md#deletecontactcategory) | **DELETE** /v1/contacts/categories/{id} | Delete a category. |
| [**getContact**](ContactsApi.md#getcontact) | **GET** /v1/contacts/{id} | Fetch a contact. |
| [**listContactCategories**](ContactsApi.md#listcontactcategories) | **GET** /v1/contacts/categories | List contact categories. Requires &#x60;organization_id&#x60; query param. |
| [**listContactProviders**](ContactsApi.md#listcontactproviders) | **GET** /v1/contacts/providers | List supported contact providers (native + OAuth-connected). |
| [**listContacts**](ContactsApi.md#listcontacts) | **GET** /v1/contacts | List the caller\&#39;s contacts (across providers). |
| [**unassignContactCategory**](ContactsApi.md#unassigncontactcategory) | **DELETE** /v1/contacts/{id}/categories/{categoryId} | Remove a category from a contact. |
| [**updateContact**](ContactsApi.md#updatecontactoperation) | **PATCH** /v1/contacts/{id} | Update a contact. |
| [**updateContactCategory**](ContactsApi.md#updatecontactcategoryoperation) | **PATCH** /v1/contacts/categories/{id} | Update a category. |



## assignContactCategory

> assignContactCategory(id, assignContactCategoryRequest)

Assign a category to a contact.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { AssignContactCategoryOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    id: id_example,
    // AssignContactCategoryRequest
    assignContactCategoryRequest: ...,
  } satisfies AssignContactCategoryOperationRequest;

  try {
    const data = await api.assignContactCategory(body);
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
| **assignContactCategoryRequest** | [AssignContactCategoryRequest](AssignContactCategoryRequest.md) |  | |

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
| **204** | Assigned. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createContact

> Contact createContact(createContactRequest)

Create a contact.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { CreateContactOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // CreateContactRequest
    createContactRequest: ...,
  } satisfies CreateContactOperationRequest;

  try {
    const data = await api.createContact(body);
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
| **createContactRequest** | [CreateContactRequest](CreateContactRequest.md) |  | |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created contact. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createContactCategory

> ContactCategory createContactCategory(createContactCategoryRequest)

Create a contact category.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { CreateContactCategoryOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // CreateContactCategoryRequest
    createContactCategoryRequest: ...,
  } satisfies CreateContactCategoryOperationRequest;

  try {
    const data = await api.createContactCategory(body);
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
| **createContactCategoryRequest** | [CreateContactCategoryRequest](CreateContactCategoryRequest.md) |  | |

### Return type

[**ContactCategory**](ContactCategory.md)

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


## deleteContact

> deleteContact(id)

Delete a contact.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { DeleteContactRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteContactRequest;

  try {
    const data = await api.deleteContact(body);
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


## deleteContactCategory

> deleteContactCategory(id)

Delete a category.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { DeleteContactCategoryRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteContactCategoryRequest;

  try {
    const data = await api.deleteContactCategory(body);
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


## getContact

> Contact getContact(id)

Fetch a contact.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { GetContactRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetContactRequest;

  try {
    const data = await api.getContact(body);
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

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listContactCategories

> ContactCategoryListResponse listContactCategories(organizationId)

List contact categories. Requires &#x60;organization_id&#x60; query param.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { ListContactCategoriesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    organizationId: organizationId_example,
  } satisfies ListContactCategoriesRequest;

  try {
    const data = await api.listContactCategories(body);
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

[**ContactCategoryListResponse**](ContactCategoryListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Category envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listContactProviders

> ContactProviderListResponse listContactProviders()

List supported contact providers (native + OAuth-connected).

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { ListContactProvidersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  try {
    const data = await api.listContactProviders();
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

[**ContactProviderListResponse**](ContactProviderListResponse.md)

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


## listContacts

> ContactListResponse listContacts(limit, provider, search)

List the caller\&#39;s contacts (across providers).

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { ListContactsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // number (optional)
    limit: 56,
    // string (optional)
    provider: provider_example,
    // string (optional)
    search: search_example,
  } satisfies ListContactsRequest;

  try {
    const data = await api.listContacts(body);
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
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |
| **provider** | `string` |  | [Optional] [Defaults to `undefined`] |
| **search** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**ContactListResponse**](ContactListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## unassignContactCategory

> unassignContactCategory(id, categoryId)

Remove a category from a contact.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { UnassignContactCategoryRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    id: id_example,
    // string
    categoryId: categoryId_example,
  } satisfies UnassignContactCategoryRequest;

  try {
    const data = await api.unassignContactCategory(body);
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
| **categoryId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Removed. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateContact

> Contact updateContact(id, updateContactRequest)

Update a contact.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { UpdateContactOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateContactRequest
    updateContactRequest: ...,
  } satisfies UpdateContactOperationRequest;

  try {
    const data = await api.updateContact(body);
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
| **updateContactRequest** | [UpdateContactRequest](UpdateContactRequest.md) |  | |

### Return type

[**Contact**](Contact.md)

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


## updateContactCategory

> ContactCategory updateContactCategory(id, updateContactCategoryRequest)

Update a category.

### Example

```ts
import {
  Configuration,
  ContactsApi,
} from '@spatio/sdk-ts';
import type { UpdateContactCategoryOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ContactsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateContactCategoryRequest
    updateContactCategoryRequest: ...,
  } satisfies UpdateContactCategoryOperationRequest;

  try {
    const data = await api.updateContactCategory(body);
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
| **updateContactCategoryRequest** | [UpdateContactCategoryRequest](UpdateContactCategoryRequest.md) |  | |

### Return type

[**ContactCategory**](ContactCategory.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated category. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

