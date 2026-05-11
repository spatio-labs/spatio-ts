# LogosApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getDomainLogo**](LogosApi.md#getdomainlogo) | **GET** /v1/logos/domain/{domain} | Resolve a domain to its logo URL (CDN-cached 24h). |
| [**getEmailLogo**](LogosApi.md#getemaillogo) | **GET** /v1/logos/email/{email} | Resolve an email address to its domain logo URL. |
| [**getLogosBatch**](LogosApi.md#getlogosbatch) | **POST** /v1/logos/batch | Batch-resolve a list of domains/emails to logo URLs in one call. |



## getDomainLogo

> GetDomainLogo200Response getDomainLogo(domain)

Resolve a domain to its logo URL (CDN-cached 24h).

### Example

```ts
import {
  Configuration,
  LogosApi,
} from '@spatio/sdk-ts';
import type { GetDomainLogoRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new LogosApi(config);

  const body = {
    // string
    domain: domain_example,
  } satisfies GetDomainLogoRequest;

  try {
    const data = await api.getDomainLogo(body);
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
| **domain** | `string` |  | [Defaults to `undefined`] |

### Return type

[**GetDomainLogo200Response**](GetDomainLogo200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Logo URL. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEmailLogo

> { [key: string]: any; } getEmailLogo(email)

Resolve an email address to its domain logo URL.

### Example

```ts
import {
  Configuration,
  LogosApi,
} from '@spatio/sdk-ts';
import type { GetEmailLogoRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new LogosApi(config);

  const body = {
    // string
    email: email_example,
  } satisfies GetEmailLogoRequest;

  try {
    const data = await api.getEmailLogo(body);
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
| **email** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Logo URL. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLogosBatch

> { [key: string]: any; } getLogosBatch(requestBody)

Batch-resolve a list of domains/emails to logo URLs in one call.

### Example

```ts
import {
  Configuration,
  LogosApi,
} from '@spatio/sdk-ts';
import type { GetLogosBatchRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new LogosApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies GetLogosBatchRequest;

  try {
    const data = await api.getLogosBatch(body);
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
| **200** | Logo map. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

