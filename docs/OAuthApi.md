# OAuthApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getJWKS**](OAuthApi.md#getjwks) | **GET** /.well-known/jwks.json | JSON Web Key Set for id_token verification (RFC 7517). |
| [**getOAuthDiscovery**](OAuthApi.md#getoauthdiscovery) | **GET** /.well-known/oauth-authorization-server | OAuth 2.1 authorization server metadata (RFC 8414). |
| [**getOpenIDConfiguration**](OAuthApi.md#getopenidconfiguration) | **GET** /.well-known/openid-configuration | OpenID Connect Discovery 1.0 metadata. |
| [**getUserInfo**](OAuthApi.md#getuserinfo) | **GET** /oauth2/userinfo | OIDC UserInfo (OpenID Connect Core 1.0 §5.3). |
| [**oauthAuthorize**](OAuthApi.md#oauthauthorize) | **GET** /oauth2/authorize | OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE). |
| [**oauthIntrospect**](OAuthApi.md#oauthintrospect) | **POST** /oauth2/introspect | RFC 7662 token introspection. Accepts both OAuth access tokens and PATs. |
| [**oauthRevoke**](OAuthApi.md#oauthrevoke) | **POST** /oauth2/revoke | RFC 7009 token revocation. Idempotent. |
| [**oauthToken**](OAuthApi.md#oauthtoken) | **POST** /oauth2/token | Exchange authorization code or refresh token for an access token (+ id_token if &#x60;openid&#x60; scope). |
| [**postUserInfo**](OAuthApi.md#postuserinfo) | **POST** /oauth2/userinfo | Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body. |
| [**registerOAuthClient**](OAuthApi.md#registeroauthclient) | **POST** /oauth2/register | Register a new OAuth 2.1 client (RFC 7591 dynamic client registration). |



## getJWKS

> JWKS getJWKS()

JSON Web Key Set for id_token verification (RFC 7517).

The set of public keys RPs use to verify Spatio-issued id_tokens. Cached for 5 minutes at the edge. Always includes the currently-active signing key plus any retired keys that may still be in circulation (id_token TTL is 1 hour + slack). 

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { GetJWKSRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  try {
    const data = await api.getJWKS();
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

[**JWKS**](JWKS.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Key set. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getOAuthDiscovery

> DiscoveryDocument getOAuthDiscovery()

OAuth 2.1 authorization server metadata (RFC 8414).

Returns the canonical metadata for the Spatio OAuth 2.1 + OpenID Connect server. Third-party RPs use this to auto-discover endpoint URLs, supported scopes, and signing algorithms.  Identical payload to &#x60;/.well-known/openid-configuration&#x60; — either path is acceptable; OIDC clients prefer the openid-configuration alias. 

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { GetOAuthDiscoveryRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  try {
    const data = await api.getOAuthDiscovery();
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

[**DiscoveryDocument**](DiscoveryDocument.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Metadata document. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getOpenIDConfiguration

> DiscoveryDocument getOpenIDConfiguration()

OpenID Connect Discovery 1.0 metadata.

Alias of &#x60;/.well-known/oauth-authorization-server&#x60;. Provided so OIDC client libraries (NextAuth, Auth.js, oidc-client-ts, passport-openidconnect) auto-detect Spatio as an OIDC provider via their &#x60;wellKnown&#x60; / &#x60;discoveryUrl&#x60; config field. 

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { GetOpenIDConfigurationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  try {
    const data = await api.getOpenIDConfiguration();
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

[**DiscoveryDocument**](DiscoveryDocument.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Metadata document. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getUserInfo

> UserInfoResponse getUserInfo()

OIDC UserInfo (OpenID Connect Core 1.0 §5.3).

Returns user claims gated by the scopes on the presenting access token. &#x60;sub&#x60; is always returned; &#x60;email&#x60;, &#x60;name&#x60;, etc. require their respective scopes. 

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { GetUserInfoRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OAuthApi(config);

  try {
    const data = await api.getUserInfo();
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

[**UserInfoResponse**](UserInfoResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User claims. |  -  |
| **401** | Token invalid. |  * WWW-Authenticate -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## oauthAuthorize

> oauthAuthorize(clientId, redirectUri, responseType, codeChallenge, codeChallengeMethod, scope, state, nonce, prompt, maxAge)

OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE).

Browser-redirect endpoint. Validates the client + redirect_uri, packs the request into a signed JWT, and 302s the user\&#39;s browser to the consent UI. The consent UI then POSTs to &#x60;/oauth2/authorize/confirm&#x60; with the user\&#39;s decision.  OIDC additions: &#x60;scope&#x3D;openid+profile+email&#x60;, &#x60;nonce&#x60;, &#x60;prompt&#x60; (none|login|consent), &#x60;max_age&#x60;. 

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { OauthAuthorizeRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  const body = {
    // string
    clientId: clientId_example,
    // string
    redirectUri: redirectUri_example,
    // 'code'
    responseType: responseType_example,
    // string
    codeChallenge: codeChallenge_example,
    // 'S256'
    codeChallengeMethod: codeChallengeMethod_example,
    // string (optional)
    scope: scope_example,
    // string (optional)
    state: state_example,
    // string (optional)
    nonce: nonce_example,
    // 'none' | 'login' | 'consent' (optional)
    prompt: prompt_example,
    // number (optional)
    maxAge: 56,
  } satisfies OauthAuthorizeRequest;

  try {
    const data = await api.oauthAuthorize(body);
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
| **clientId** | `string` |  | [Defaults to `undefined`] |
| **redirectUri** | `string` |  | [Defaults to `undefined`] |
| **responseType** | `code` |  | [Defaults to `undefined`] [Enum: code] |
| **codeChallenge** | `string` |  | [Defaults to `undefined`] |
| **codeChallengeMethod** | `S256` |  | [Defaults to `undefined`] [Enum: S256] |
| **scope** | `string` |  | [Optional] [Defaults to `undefined`] |
| **state** | `string` |  | [Optional] [Defaults to `undefined`] |
| **nonce** | `string` |  | [Optional] [Defaults to `undefined`] |
| **prompt** | `none`, `login`, `consent` |  | [Optional] [Defaults to `undefined`] [Enum: none, login, consent] |
| **maxAge** | `number` |  | [Optional] [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **302** | Redirect to consent UI or back to redirect_uri with error. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## oauthIntrospect

> IntrospectionResponse oauthIntrospect(token)

RFC 7662 token introspection. Accepts both OAuth access tokens and PATs.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { OauthIntrospectRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  const body = {
    // string
    token: token_example,
  } satisfies OauthIntrospectRequest;

  try {
    const data = await api.oauthIntrospect(body);
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
| **token** | `string` |  | [Defaults to `undefined`] |

### Return type

[**IntrospectionResponse**](IntrospectionResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Introspection result. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## oauthRevoke

> oauthRevoke(token)

RFC 7009 token revocation. Idempotent.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { OauthRevokeRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  const body = {
    // string
    token: token_example,
  } satisfies OauthRevokeRequest;

  try {
    const data = await api.oauthRevoke(body);
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
| **token** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Revoked (or no-op). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## oauthToken

> TokenResponse oauthToken(grantType, code, codeVerifier, redirectUri, refreshToken, clientId, clientSecret)

Exchange authorization code or refresh token for an access token (+ id_token if &#x60;openid&#x60; scope).

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { OauthTokenRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  const body = {
    // string
    grantType: grantType_example,
    // string | Required for authorization_code grant. (optional)
    code: code_example,
    // string | PKCE verifier — required for authorization_code grant. (optional)
    codeVerifier: codeVerifier_example,
    // string (optional)
    redirectUri: redirectUri_example,
    // string | Required for refresh_token grant. (optional)
    refreshToken: refreshToken_example,
    // string (optional)
    clientId: clientId_example,
    // string (optional)
    clientSecret: clientSecret_example,
  } satisfies OauthTokenRequest;

  try {
    const data = await api.oauthToken(body);
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
| **grantType** | `authorization_code`, `refresh_token` |  | [Defaults to `undefined`] [Enum: authorization_code, refresh_token] |
| **code** | `string` | Required for authorization_code grant. | [Optional] [Defaults to `undefined`] |
| **codeVerifier** | `string` | PKCE verifier — required for authorization_code grant. | [Optional] [Defaults to `undefined`] |
| **redirectUri** | `string` |  | [Optional] [Defaults to `undefined`] |
| **refreshToken** | `string` | Required for refresh_token grant. | [Optional] [Defaults to `undefined`] |
| **clientId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **clientSecret** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**TokenResponse**](TokenResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Token pair (and id_token when applicable). |  -  |
| **400** | Invalid grant. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## postUserInfo

> UserInfoResponse postUserInfo()

Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { PostUserInfoRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OAuthApi(config);

  try {
    const data = await api.postUserInfo();
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

[**UserInfoResponse**](UserInfoResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User claims. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## registerOAuthClient

> ClientRegistrationResponse registerOAuthClient(clientRegistrationRequest)

Register a new OAuth 2.1 client (RFC 7591 dynamic client registration).

Returns a fresh &#x60;client_id&#x60; (and, for confidential clients, &#x60;client_secret&#x60;) plus a one-time &#x60;registration_access_token&#x60; the client can use later to update its registration. Public clients (mobile, SPA) MUST use &#x60;token_endpoint_auth_method: none&#x60; and PKCE.  Rate-limited to 10 registrations per hour per source IP. 

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@spatio/sdk-ts';
import type { RegisterOAuthClientRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const api = new OAuthApi();

  const body = {
    // ClientRegistrationRequest
    clientRegistrationRequest: ...,
  } satisfies RegisterOAuthClientRequest;

  try {
    const data = await api.registerOAuthClient(body);
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
| **clientRegistrationRequest** | [ClientRegistrationRequest](ClientRegistrationRequest.md) |  | |

### Return type

[**ClientRegistrationResponse**](ClientRegistrationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Client registered. |  -  |
| **400** | Invalid metadata. |  -  |
| **429** | Rate limit exceeded. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

