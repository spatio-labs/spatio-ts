# OrganizationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**acceptOrganizationInvitation**](OrganizationsApi.md#acceptorganizationinvitationoperation) | **POST** /v1/organizations/{org}/accept-invitation | Accept an invitation to this organization. |
| [**addOrganizationMember**](OrganizationsApi.md#addorganizationmemberoperation) | **POST** /v1/organizations/{org}/members | Add a member directly (skips invitation flow). |
| [**createOrganization**](OrganizationsApi.md#createorganizationoperation) | **POST** /v1/organizations | Create an organization. |
| [**createOrganizationConcept**](OrganizationsApi.md#createorganizationconcept) | **POST** /v1/organizations/{org}/concepts | Create an org-brain concept (admin+ only). |
| [**createOrganizationCustomRole**](OrganizationsApi.md#createorganizationcustomrole) | **POST** /v1/organizations/{org}/roles | Create a custom role (admin+ only). |
| [**createOrganizationInvitation**](OrganizationsApi.md#createorganizationinvitationoperation) | **POST** /v1/organizations/{org}/invitations | Invite a user to the organization. |
| [**createOrganizationWorkspace**](OrganizationsApi.md#createorganizationworkspace) | **POST** /v1/organizations/{org}/workspaces | Create a workspace inside an organization. |
| [**deleteOrganization**](OrganizationsApi.md#deleteorganization) | **DELETE** /v1/organizations/{org} | Delete an organization. |
| [**deleteOrganizationConcept**](OrganizationsApi.md#deleteorganizationconcept) | **DELETE** /v1/organizations/{org}/concepts/{slug} | Delete a concept (admin+ only). |
| [**deleteOrganizationCustomRole**](OrganizationsApi.md#deleteorganizationcustomrole) | **DELETE** /v1/organizations/{org}/roles/{roleId} | Delete a custom role (admin+ only). |
| [**deleteOrganizationLogo**](OrganizationsApi.md#deleteorganizationlogo) | **DELETE** /v1/organizations/{org}/logo | Delete the organization logo. |
| [**getOrganization**](OrganizationsApi.md#getorganization) | **GET** /v1/organizations/{org} | Fetch a single organization. |
| [**getOrganizationConcept**](OrganizationsApi.md#getorganizationconcept) | **GET** /v1/organizations/{org}/concepts/{slug} | Fetch a concept. |
| [**listMyOrganizations**](OrganizationsApi.md#listmyorganizations) | **GET** /v1/organizations | List the caller\&#39;s organizations. |
| [**listOrganizationAuditLog**](OrganizationsApi.md#listorganizationauditlog) | **GET** /v1/organizations/{org}/audit-log | Read the organization audit log (admin / billing-admin only). |
| [**listOrganizationConcepts**](OrganizationsApi.md#listorganizationconcepts) | **GET** /v1/organizations/{org}/concepts | List org-brain concepts (curated knowledge surfaced to agents). |
| [**listOrganizationCustomRoles**](OrganizationsApi.md#listorganizationcustomroles) | **GET** /v1/organizations/{org}/roles | List custom roles defined on the organization. |
| [**listOrganizationInvitations**](OrganizationsApi.md#listorganizationinvitations) | **GET** /v1/organizations/{org}/invitations | List pending invitations for an organization. |
| [**listOrganizationMembers**](OrganizationsApi.md#listorganizationmembers) | **GET** /v1/organizations/{org}/members | List members of an organization. |
| [**listOrganizationWorkspaces**](OrganizationsApi.md#listorganizationworkspaces) | **GET** /v1/organizations/{org}/workspaces | List workspaces in an organization. |
| [**removeOrganizationMember**](OrganizationsApi.md#removeorganizationmember) | **DELETE** /v1/organizations/{org}/members/{memberId} | Remove a member from the organization. |
| [**resendOrganizationInvitation**](OrganizationsApi.md#resendorganizationinvitation) | **POST** /v1/organizations/{org}/invitations/{invitationId}/resend | Revoke and reissue an invitation with a fresh token. |
| [**revokeOrganizationInvitation**](OrganizationsApi.md#revokeorganizationinvitation) | **DELETE** /v1/organizations/{org}/invitations/{invitationId} | Revoke a pending invitation. |
| [**updateOrganization**](OrganizationsApi.md#updateorganizationoperation) | **PATCH** /v1/organizations/{org} | Update organization metadata. |
| [**updateOrganizationConcept**](OrganizationsApi.md#updateorganizationconcept) | **PATCH** /v1/organizations/{org}/concepts/{slug} | Update a concept (admin+ only). |
| [**updateOrganizationCustomRole**](OrganizationsApi.md#updateorganizationcustomrole) | **PATCH** /v1/organizations/{org}/roles/{roleId} | Update a custom role (admin+ only). |
| [**updateOrganizationMember**](OrganizationsApi.md#updateorganizationmemberoperation) | **PATCH** /v1/organizations/{org}/members/{memberId} | Update a member\&#39;s role. |
| [**uploadOrganizationLogo**](OrganizationsApi.md#uploadorganizationlogo) | **POST** /v1/organizations/{org}/logo | Upload (or replace) the organization logo. Multipart. |



## acceptOrganizationInvitation

> { [key: string]: any; } acceptOrganizationInvitation(org, acceptOrganizationInvitationRequest)

Accept an invitation to this organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { AcceptOrganizationInvitationOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // AcceptOrganizationInvitationRequest
    acceptOrganizationInvitationRequest: ...,
  } satisfies AcceptOrganizationInvitationOperationRequest;

  try {
    const data = await api.acceptOrganizationInvitation(body);
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
| **acceptOrganizationInvitationRequest** | [AcceptOrganizationInvitationRequest](AcceptOrganizationInvitationRequest.md) |  | |

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
| **200** | Invitation accepted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **410** | Invitation already accepted, revoked, or expired. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## addOrganizationMember

> { [key: string]: any; } addOrganizationMember(org, addOrganizationMemberRequest)

Add a member directly (skips invitation flow).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { AddOrganizationMemberOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // AddOrganizationMemberRequest
    addOrganizationMemberRequest: ...,
  } satisfies AddOrganizationMemberOperationRequest;

  try {
    const data = await api.addOrganizationMember(body);
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
| **addOrganizationMemberRequest** | [AddOrganizationMemberRequest](AddOrganizationMemberRequest.md) |  | |

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
| **200** | Member added. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **402** | Seat cap exceeded on free tier. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createOrganization

> { [key: string]: any; } createOrganization(createOrganizationRequest)

Create an organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { CreateOrganizationOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // CreateOrganizationRequest
    createOrganizationRequest: ...,
  } satisfies CreateOrganizationOperationRequest;

  try {
    const data = await api.createOrganization(body);
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
| **createOrganizationRequest** | [CreateOrganizationRequest](CreateOrganizationRequest.md) |  | |

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
| **201** | Organization created (with optional default workspace). |  -  |
| **400** | Invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createOrganizationConcept

> { [key: string]: any; } createOrganizationConcept(org, requestBody)

Create an org-brain concept (admin+ only).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { CreateOrganizationConceptRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateOrganizationConceptRequest;

  try {
    const data = await api.createOrganizationConcept(body);
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
| **201** | Created. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createOrganizationCustomRole

> { [key: string]: any; } createOrganizationCustomRole(org, requestBody)

Create a custom role (admin+ only).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { CreateOrganizationCustomRoleRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateOrganizationCustomRoleRequest;

  try {
    const data = await api.createOrganizationCustomRole(body);
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
| **201** | Created. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createOrganizationInvitation

> OrganizationInvitation createOrganizationInvitation(org, createOrganizationInvitationRequest)

Invite a user to the organization.

Pending invitations count toward seat cap. Free-tier callers at the cap receive a &#x60;402&#x60; with billing-upgrade payload; paid-tier auto-scales the Stripe quantity. 

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { CreateOrganizationInvitationOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // CreateOrganizationInvitationRequest
    createOrganizationInvitationRequest: ...,
  } satisfies CreateOrganizationInvitationOperationRequest;

  try {
    const data = await api.createOrganizationInvitation(body);
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
| **createOrganizationInvitationRequest** | [CreateOrganizationInvitationRequest](CreateOrganizationInvitationRequest.md) |  | |

### Return type

[**OrganizationInvitation**](OrganizationInvitation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation created. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **402** | Seat cap exceeded on free tier. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createOrganizationWorkspace

> WorkspaceEnvelope createOrganizationWorkspace(org, createWorkspaceRequest)

Create a workspace inside an organization.

Requires the &#x60;OrgActionCreateWorkspace&#x60; action permission. Slug collisions auto-suffix (&#x60;-2&#x60;, &#x60;-3&#x60;, ...). 

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { CreateOrganizationWorkspaceRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // CreateWorkspaceRequest
    createWorkspaceRequest: ...,
  } satisfies CreateOrganizationWorkspaceRequest;

  try {
    const data = await api.createOrganizationWorkspace(body);
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
| **createWorkspaceRequest** | [CreateWorkspaceRequest](CreateWorkspaceRequest.md) |  | |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Workspace created. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteOrganization

> deleteOrganization(org)

Delete an organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { DeleteOrganizationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string | Organization id or slug.
    org: org_example,
  } satisfies DeleteOrganizationRequest;

  try {
    const data = await api.deleteOrganization(body);
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
| **org** | `string` | Organization id or slug. | [Defaults to `undefined`] |

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
| **204** | Organization deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteOrganizationConcept

> deleteOrganizationConcept(org, slug)

Delete a concept (admin+ only).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { DeleteOrganizationConceptRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    slug: slug_example,
  } satisfies DeleteOrganizationConceptRequest;

  try {
    const data = await api.deleteOrganizationConcept(body);
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
| **slug** | `string` |  | [Defaults to `undefined`] |

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


## deleteOrganizationCustomRole

> deleteOrganizationCustomRole(org, roleId)

Delete a custom role (admin+ only).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { DeleteOrganizationCustomRoleRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    roleId: roleId_example,
  } satisfies DeleteOrganizationCustomRoleRequest;

  try {
    const data = await api.deleteOrganizationCustomRole(body);
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
| **roleId** | `string` |  | [Defaults to `undefined`] |

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


## deleteOrganizationLogo

> deleteOrganizationLogo(org)

Delete the organization logo.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { DeleteOrganizationLogoRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
  } satisfies DeleteOrganizationLogoRequest;

  try {
    const data = await api.deleteOrganizationLogo(body);
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


## getOrganization

> OrganizationDetailLegacy getOrganization(org)

Fetch a single organization.

**Wire format note:** response uses PascalCase keys (&#x60;ID&#x60;, &#x60;Name&#x60;, &#x60;Slug&#x60;, ...) — distinct from the rest of the SpatioAPI\&#39;s camelCase convention. Documented as-is; a future cleanup will harmonize. 

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { GetOrganizationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string | Organization id or slug.
    org: org_example,
  } satisfies GetOrganizationRequest;

  try {
    const data = await api.getOrganization(body);
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
| **org** | `string` | Organization id or slug. | [Defaults to `undefined`] |

### Return type

[**OrganizationDetailLegacy**](OrganizationDetailLegacy.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The organization (PascalCase). |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not a member of this organization. |  -  |
| **404** | Organization not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getOrganizationConcept

> { [key: string]: any; } getOrganizationConcept(org, slug)

Fetch a concept.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { GetOrganizationConceptRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    slug: slug_example,
  } satisfies GetOrganizationConceptRequest;

  try {
    const data = await api.getOrganizationConcept(body);
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
| **slug** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Concept. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listMyOrganizations

> OrganizationListResponse listMyOrganizations()

List the caller\&#39;s organizations.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ListMyOrganizationsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  try {
    const data = await api.listMyOrganizations();
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

[**OrganizationListResponse**](OrganizationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Organization list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOrganizationAuditLog

> { [key: string]: any; } listOrganizationAuditLog(org, limit, cursor)

Read the organization audit log (admin / billing-admin only).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ListOrganizationAuditLogRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // number (optional)
    limit: 56,
    // string (optional)
    cursor: cursor_example,
  } satisfies ListOrganizationAuditLogRequest;

  try {
    const data = await api.listOrganizationAuditLog(body);
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
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |
| **cursor** | `string` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Audit envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOrganizationConcepts

> { [key: string]: any; } listOrganizationConcepts(org)

List org-brain concepts (curated knowledge surfaced to agents).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ListOrganizationConceptsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
  } satisfies ListOrganizationConceptsRequest;

  try {
    const data = await api.listOrganizationConcepts(body);
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
| **200** | Concept envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOrganizationCustomRoles

> { [key: string]: any; } listOrganizationCustomRoles(org)

List custom roles defined on the organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ListOrganizationCustomRolesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
  } satisfies ListOrganizationCustomRolesRequest;

  try {
    const data = await api.listOrganizationCustomRoles(body);
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
| **200** | Role envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOrganizationInvitations

> OrganizationInvitationListResponse listOrganizationInvitations(org)

List pending invitations for an organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ListOrganizationInvitationsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
  } satisfies ListOrganizationInvitationsRequest;

  try {
    const data = await api.listOrganizationInvitations(body);
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

### Return type

[**OrganizationInvitationListResponse**](OrganizationInvitationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOrganizationMembers

> OrganizationMemberListResponse listOrganizationMembers(org)

List members of an organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ListOrganizationMembersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
  } satisfies ListOrganizationMembersRequest;

  try {
    const data = await api.listOrganizationMembers(body);
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

### Return type

[**OrganizationMemberListResponse**](OrganizationMemberListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Member list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOrganizationWorkspaces

> WorkspaceListResponse listOrganizationWorkspaces(org)

List workspaces in an organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ListOrganizationWorkspacesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
  } satisfies ListOrganizationWorkspacesRequest;

  try {
    const data = await api.listOrganizationWorkspaces(body);
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

### Return type

[**WorkspaceListResponse**](WorkspaceListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Workspace list with member counts. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not a member of this organization. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## removeOrganizationMember

> removeOrganizationMember(org, memberId)

Remove a member from the organization.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { RemoveOrganizationMemberRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    memberId: memberId_example,
  } satisfies RemoveOrganizationMemberRequest;

  try {
    const data = await api.removeOrganizationMember(body);
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
| **memberId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Member removed. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resendOrganizationInvitation

> OrganizationInvitation resendOrganizationInvitation(org, invitationId)

Revoke and reissue an invitation with a fresh token.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { ResendOrganizationInvitationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    invitationId: invitationId_example,
  } satisfies ResendOrganizationInvitationRequest;

  try {
    const data = await api.resendOrganizationInvitation(body);
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
| **invitationId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**OrganizationInvitation**](OrganizationInvitation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | New invitation. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Invitation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeOrganizationInvitation

> revokeOrganizationInvitation(org, invitationId)

Revoke a pending invitation.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { RevokeOrganizationInvitationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    invitationId: invitationId_example,
  } satisfies RevokeOrganizationInvitationRequest;

  try {
    const data = await api.revokeOrganizationInvitation(body);
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
| **invitationId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Invitation revoked. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Invitation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateOrganization

> { [key: string]: any; } updateOrganization(org, updateOrganizationRequest)

Update organization metadata.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { UpdateOrganizationOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string | Organization id or slug.
    org: org_example,
    // UpdateOrganizationRequest
    updateOrganizationRequest: ...,
  } satisfies UpdateOrganizationOperationRequest;

  try {
    const data = await api.updateOrganization(body);
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
| **org** | `string` | Organization id or slug. | [Defaults to `undefined`] |
| **updateOrganizationRequest** | [UpdateOrganizationRequest](UpdateOrganizationRequest.md) |  | |

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
| **200** | Updated org. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateOrganizationConcept

> { [key: string]: any; } updateOrganizationConcept(org, slug, requestBody)

Update a concept (admin+ only).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { UpdateOrganizationConceptRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    slug: slug_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies UpdateOrganizationConceptRequest;

  try {
    const data = await api.updateOrganizationConcept(body);
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
| **slug** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateOrganizationCustomRole

> { [key: string]: any; } updateOrganizationCustomRole(org, roleId, requestBody)

Update a custom role (admin+ only).

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { UpdateOrganizationCustomRoleRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    roleId: roleId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies UpdateOrganizationCustomRoleRequest;

  try {
    const data = await api.updateOrganizationCustomRole(body);
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
| **roleId** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Updated. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateOrganizationMember

> { [key: string]: any; } updateOrganizationMember(org, memberId, updateOrganizationMemberRequest)

Update a member\&#39;s role.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { UpdateOrganizationMemberOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    memberId: memberId_example,
    // UpdateOrganizationMemberRequest
    updateOrganizationMemberRequest: ...,
  } satisfies UpdateOrganizationMemberOperationRequest;

  try {
    const data = await api.updateOrganizationMember(body);
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
| **memberId** | `string` |  | [Defaults to `undefined`] |
| **updateOrganizationMemberRequest** | [UpdateOrganizationMemberRequest](UpdateOrganizationMemberRequest.md) |  | |

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
| **200** | Member updated. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## uploadOrganizationLogo

> { [key: string]: any; } uploadOrganizationLogo(org, file)

Upload (or replace) the organization logo. Multipart.

### Example

```ts
import {
  Configuration,
  OrganizationsApi,
} from '@spatio/sdk-ts';
import type { UploadOrganizationLogoRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OrganizationsApi(config);

  const body = {
    // string
    org: org_example,
    // Blob (optional)
    file: BINARY_DATA_HERE,
  } satisfies UploadOrganizationLogoRequest;

  try {
    const data = await api.uploadOrganizationLogo(body);
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
| **200** | Uploaded. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

