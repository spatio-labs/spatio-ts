# WorkspacesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**acceptWorkspaceInvitation**](WorkspacesApi.md#acceptworkspaceinvitation) | **POST** /v1/invitations/{token}/accept | Accept a workspace invitation by token. The signed-in user\&#39;s email must match the invitation. Organization-token accept lives at &#x60;POST /v1/organizations/{org}/accept-invitation&#x60;.  |
| [**addWorkspaceMember**](WorkspacesApi.md#addworkspacememberoperation) | **POST** /v1/workspaces/{workspaceId}/members | Add a member directly (skips invitation flow). |
| [**createWorkspace**](WorkspacesApi.md#createworkspaceoperation) | **POST** /v1/workspaces | Create a workspace. Requires &#x60;organizationId&#x60; in the body — bare \&quot;personal\&quot; workspaces aren\&#39;t supported on the public API.  |
| [**createWorkspaceInvitation**](WorkspacesApi.md#createworkspaceinvitationoperation) | **POST** /v1/workspaces/{workspaceId}/invitations | Invite a user to a workspace. |
| [**getPublicInvitation**](WorkspacesApi.md#getpublicinvitation) | **GET** /invitations/{token} | Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in.  |
| [**getWorkspace**](WorkspacesApi.md#getworkspace) | **GET** /v1/workspaces/{workspaceId} | Fetch a single workspace by id. |
| [**listMyWorkspaces**](WorkspacesApi.md#listmyworkspaces) | **GET** /v1/workspaces | List the caller\&#39;s workspaces (across organizations). |
| [**listWorkspaceInvitations**](WorkspacesApi.md#listworkspaceinvitations) | **GET** /v1/workspaces/{workspaceId}/invitations | List pending workspace invitations. |
| [**listWorkspaceMembers**](WorkspacesApi.md#listworkspacemembers) | **GET** /v1/workspaces/{workspaceId}/members | List members of a workspace. |
| [**removeWorkspaceMember**](WorkspacesApi.md#removeworkspacemember) | **DELETE** /v1/workspaces/{workspaceId}/members/{memberId} | Remove a member from the workspace. |
| [**revokeWorkspaceInvitation**](WorkspacesApi.md#revokeworkspaceinvitation) | **DELETE** /v1/workspaces/{workspaceId}/invitations/{invitationId} | Revoke a pending workspace invitation. |
| [**updateWorkspace**](WorkspacesApi.md#updateworkspaceoperation) | **PATCH** /v1/workspaces/{workspaceId} | Update workspace metadata. |
| [**updateWorkspaceMember**](WorkspacesApi.md#updateworkspacememberoperation) | **PATCH** /v1/workspaces/{workspaceId}/members/{memberId} | Update a member\&#39;s role. |



## acceptWorkspaceInvitation

> { [key: string]: any; } acceptWorkspaceInvitation(token)

Accept a workspace invitation by token. The signed-in user\&#39;s email must match the invitation. Organization-token accept lives at &#x60;POST /v1/organizations/{org}/accept-invitation&#x60;. 

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { AcceptWorkspaceInvitationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    token: token_example,
  } satisfies AcceptWorkspaceInvitationRequest;

  try {
    const data = await api.acceptWorkspaceInvitation(body);
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation accepted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Invitation not found. |  -  |
| **410** | Invitation already accepted, revoked, or expired. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## addWorkspaceMember

> { [key: string]: any; } addWorkspaceMember(workspaceId, addWorkspaceMemberRequest)

Add a member directly (skips invitation flow).

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { AddWorkspaceMemberOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // AddWorkspaceMemberRequest
    addWorkspaceMemberRequest: ...,
  } satisfies AddWorkspaceMemberOperationRequest;

  try {
    const data = await api.addWorkspaceMember(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |
| **addWorkspaceMemberRequest** | [AddWorkspaceMemberRequest](AddWorkspaceMemberRequest.md) |  | |

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
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createWorkspace

> WorkspaceEnvelope createWorkspace(createWorkspaceRequest)

Create a workspace. Requires &#x60;organizationId&#x60; in the body — bare \&quot;personal\&quot; workspaces aren\&#39;t supported on the public API. 

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { CreateWorkspaceOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // CreateWorkspaceRequest
    createWorkspaceRequest: ...,
  } satisfies CreateWorkspaceOperationRequest;

  try {
    const data = await api.createWorkspace(body);
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
| **400** | Invalid body or missing organizationId. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role in the target organization. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createWorkspaceInvitation

> WorkspaceInvitation createWorkspaceInvitation(workspaceId, createWorkspaceInvitationRequest)

Invite a user to a workspace.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { CreateWorkspaceInvitationOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // CreateWorkspaceInvitationRequest
    createWorkspaceInvitationRequest: ...,
  } satisfies CreateWorkspaceInvitationOperationRequest;

  try {
    const data = await api.createWorkspaceInvitation(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |
| **createWorkspaceInvitationRequest** | [CreateWorkspaceInvitationRequest](CreateWorkspaceInvitationRequest.md) |  | |

### Return type

[**WorkspaceInvitation**](WorkspaceInvitation.md)

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


## getPublicInvitation

> PublicInvitationPayload getPublicInvitation(token)

Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. 

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { GetPublicInvitationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    token: token_example,
  } satisfies GetPublicInvitationRequest;

  try {
    const data = await api.getPublicInvitation(body);
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

[**PublicInvitationPayload**](PublicInvitationPayload.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invitation payload (workspace or organization). |  -  |
| **404** | Invitation not found. |  -  |
| **410** | Invitation already accepted, revoked, or expired. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWorkspace

> WorkspaceEnvelope getWorkspace(workspaceId)

Fetch a single workspace by id.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { GetWorkspaceRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
  } satisfies GetWorkspaceRequest;

  try {
    const data = await api.getWorkspace(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Workspace envelope. The &#x60;workspace&#x60; payload includes a compact &#x60;organization&#x60; summary and the caller\&#39;s &#x60;role&#x60;.  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Caller is not a member of this workspace. |  -  |
| **404** | Workspace not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listMyWorkspaces

> WorkspaceListResponse listMyWorkspaces()

List the caller\&#39;s workspaces (across organizations).

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { ListMyWorkspacesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  try {
    const data = await api.listMyWorkspaces();
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

[**WorkspaceListResponse**](WorkspaceListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Workspace list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listWorkspaceInvitations

> WorkspaceInvitationListResponse listWorkspaceInvitations(workspaceId)

List pending workspace invitations.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { ListWorkspaceInvitationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
  } satisfies ListWorkspaceInvitationsRequest;

  try {
    const data = await api.listWorkspaceInvitations(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**WorkspaceInvitationListResponse**](WorkspaceInvitationListResponse.md)

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


## listWorkspaceMembers

> WorkspaceMemberListResponse listWorkspaceMembers(workspaceId)

List members of a workspace.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { ListWorkspaceMembersRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
  } satisfies ListWorkspaceMembersRequest;

  try {
    const data = await api.listWorkspaceMembers(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**WorkspaceMemberListResponse**](WorkspaceMemberListResponse.md)

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


## removeWorkspaceMember

> removeWorkspaceMember(workspaceId, memberId)

Remove a member from the workspace.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { RemoveWorkspaceMemberRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // string
    memberId: memberId_example,
  } satisfies RemoveWorkspaceMemberRequest;

  try {
    const data = await api.removeWorkspaceMember(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |
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


## revokeWorkspaceInvitation

> revokeWorkspaceInvitation(workspaceId, invitationId)

Revoke a pending workspace invitation.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { RevokeWorkspaceInvitationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // string
    invitationId: invitationId_example,
  } satisfies RevokeWorkspaceInvitationRequest;

  try {
    const data = await api.revokeWorkspaceInvitation(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |
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


## updateWorkspace

> WorkspaceEnvelope updateWorkspace(workspaceId, updateWorkspaceRequest)

Update workspace metadata.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateWorkspaceOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // UpdateWorkspaceRequest
    updateWorkspaceRequest: ...,
  } satisfies UpdateWorkspaceOperationRequest;

  try {
    const data = await api.updateWorkspace(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |
| **updateWorkspaceRequest** | [UpdateWorkspaceRequest](UpdateWorkspaceRequest.md) |  | |

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
| **200** | Updated workspace envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **403** | Insufficient role. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateWorkspaceMember

> { [key: string]: any; } updateWorkspaceMember(workspaceId, memberId, updateWorkspaceMemberRequest)

Update a member\&#39;s role.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateWorkspaceMemberOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string
    workspaceId: workspaceId_example,
    // string
    memberId: memberId_example,
    // UpdateWorkspaceMemberRequest
    updateWorkspaceMemberRequest: ...,
  } satisfies UpdateWorkspaceMemberOperationRequest;

  try {
    const data = await api.updateWorkspaceMember(body);
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
| **workspaceId** | `string` |  | [Defaults to `undefined`] |
| **memberId** | `string` |  | [Defaults to `undefined`] |
| **updateWorkspaceMemberRequest** | [UpdateWorkspaceMemberRequest](UpdateWorkspaceMemberRequest.md) |  | |

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

