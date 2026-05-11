# ChannelsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createChannel**](ChannelsApi.md#createchanneloperation) | **POST** /v1/channels | Create a channel. |
| [**executeChannelAction**](ChannelsApi.md#executechannelaction) | **POST** /v1/channels/execute | Dispatch a channel action by id. |
| [**joinChannel**](ChannelsApi.md#joinchannel) | **POST** /v1/channels/{id}/join | Join a channel. |
| [**leaveChannel**](ChannelsApi.md#leavechannel) | **POST** /v1/channels/{id}/leave | Leave a channel. |
| [**listChannelActions**](ChannelsApi.md#listchannelactions) | **GET** /v1/channels/actions | Discover the action catalog for the Channels platform. |
| [**listChannelMessages**](ChannelsApi.md#listchannelmessages) | **GET** /v1/channels/messages | List messages in a channel. |
| [**listChannels**](ChannelsApi.md#listchannels) | **GET** /v1/channels | List group channels across connected chat providers. |
| [**sendChannelMessage**](ChannelsApi.md#sendchannelmessage) | **POST** /v1/channels/messages | Send a message to a channel. |
| [**workspaceCreateChannel**](ChannelsApi.md#workspacecreatechannel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels |  |
| [**workspaceExecuteChannelAction**](ChannelsApi.md#workspaceexecutechannelaction) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/execute |  |
| [**workspaceJoinChannel**](ChannelsApi.md#workspacejoinchannel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/{id}/join |  |
| [**workspaceLeaveChannel**](ChannelsApi.md#workspaceleavechannel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/{id}/leave |  |
| [**workspaceListChannelActions**](ChannelsApi.md#workspacelistchannelactions) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels/actions |  |
| [**workspaceListChannelMessages**](ChannelsApi.md#workspacelistchannelmessages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels/messages |  |
| [**workspaceListChannels**](ChannelsApi.md#workspacelistchannels) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels |  |
| [**workspaceSendChannelMessage**](ChannelsApi.md#workspacesendchannelmessage) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/messages |  |



## createChannel

> CreateChannelResponse createChannel(createChannelRequest)

Create a channel.

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateChannelOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // CreateChannelRequest
    createChannelRequest: ...,
  } satisfies CreateChannelOperationRequest;

  try {
    const data = await api.createChannel(body);
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
| **createChannelRequest** | [CreateChannelRequest](CreateChannelRequest.md) |  | |

### Return type

[**CreateChannelResponse**](CreateChannelResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Channel created. |  -  |
| **400** | Invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## executeChannelAction

> ExecuteChatActionResponse executeChannelAction(executeChatActionRequest)

Dispatch a channel action by id.

Generic action-execution endpoint. &#x60;params&#x60; shape varies per &#x60;action_id&#x60;; consult &#x60;GET /v1/channels/actions&#x60; for the per-id contract. 

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { ExecuteChannelActionRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // ExecuteChatActionRequest
    executeChatActionRequest: ...,
  } satisfies ExecuteChannelActionRequest;

  try {
    const data = await api.executeChannelAction(body);
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
| **executeChatActionRequest** | [ExecuteChatActionRequest](ExecuteChatActionRequest.md) |  | |

### Return type

[**ExecuteChatActionResponse**](ExecuteChatActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Action result. |  -  |
| **400** | Invalid body or unknown action_id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## joinChannel

> SuccessFlag joinChannel(id, channelMembershipRequest)

Join a channel.

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { JoinChannelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string | Channel id (provider-scoped).
    id: id_example,
    // ChannelMembershipRequest (optional)
    channelMembershipRequest: ...,
  } satisfies JoinChannelRequest;

  try {
    const data = await api.joinChannel(body);
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
| **id** | `string` | Channel id (provider-scoped). | [Defaults to `undefined`] |
| **channelMembershipRequest** | [ChannelMembershipRequest](ChannelMembershipRequest.md) |  | [Optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **400** | Missing or invalid id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## leaveChannel

> SuccessFlag leaveChannel(id, channelMembershipRequest)

Leave a channel.

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { LeaveChannelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string | Channel id (provider-scoped).
    id: id_example,
    // ChannelMembershipRequest (optional)
    channelMembershipRequest: ...,
  } satisfies LeaveChannelRequest;

  try {
    const data = await api.leaveChannel(body);
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
| **id** | `string` | Channel id (provider-scoped). | [Defaults to `undefined`] |
| **channelMembershipRequest** | [ChannelMembershipRequest](ChannelMembershipRequest.md) |  | [Optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success ack. |  -  |
| **400** | Missing or invalid id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listChannelActions

> ChatActionsList listChannelActions()

Discover the action catalog for the Channels platform.

Returns the action descriptors the agent layer dispatches via &#x60;POST /v1/channels/execute&#x60;. Same pattern as the DirectMessages action surface. 

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { ListChannelActionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  try {
    const data = await api.listChannelActions();
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

[**ChatActionsList**](ChatActionsList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Action catalog. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listChannelMessages

> ListMessagesResponse listChannelMessages(channel, accountId, accountIds, providers, xWorkspaceID, limit, cursor, oldestFirst)

List messages in a channel.

Channel ids are provider-scoped; pass &#x60;?accountId&#x3D;&#x60; (preferred) or &#x60;?accountIds&#x3D;&#x60; to disambiguate when the same id exists on multiple connected accounts (rare). 

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { ListChannelMessagesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string | Channel id.
    channel: channel_example,
    // string (optional)
    accountId: accountId_example,
    // Array<string> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.  (optional)
    accountIds: ...,
    // Array<string> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`). (optional)
    providers: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // number (optional)
    limit: 56,
    // string (optional)
    cursor: cursor_example,
    // boolean (optional)
    oldestFirst: true,
  } satisfies ListChannelMessagesRequest;

  try {
    const data = await api.listChannelMessages(body);
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
| **channel** | `string` | Channel id. | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **accountIds** | `Array<string>` | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [Optional] |
| **providers** | `Array<string>` | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [Optional] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |
| **cursor** | `string` |  | [Optional] [Defaults to `undefined`] |
| **oldestFirst** | `boolean` |  | [Optional] [Defaults to `false`] |

### Return type

[**ListMessagesResponse**](ListMessagesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message list. |  -  |
| **400** | Missing channel id. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listChannels

> ListChannelsResponse listChannels(accountIds, providers, xWorkspaceID, limit, cursor, includeArchived, types)

List group channels across connected chat providers.

Fan-out list. The Channels surface filters to channel-type conversations only (&#x60;type: channel | private&#x60;); for direct messages use &#x60;/v1/direct-messages&#x60;. 

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { ListChannelsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // Array<string> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.  (optional)
    accountIds: ...,
    // Array<string> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`). (optional)
    providers: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // number (optional)
    limit: 56,
    // string | Provider-specific pagination cursor. (optional)
    cursor: cursor_example,
    // boolean (optional)
    includeArchived: true,
    // Array<string> | Repeatable filter on `Channel.type`. Defaults applied by the platform exclude DMs; passing this overrides.  (optional)
    types: ...,
  } satisfies ListChannelsRequest;

  try {
    const data = await api.listChannels(body);
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
| **accountIds** | `Array<string>` | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [Optional] |
| **providers** | `Array<string>` | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [Optional] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |
| **cursor** | `string` | Provider-specific pagination cursor. | [Optional] [Defaults to `undefined`] |
| **includeArchived** | `boolean` |  | [Optional] [Defaults to `false`] |
| **types** | `Array<string>` | Repeatable filter on &#x60;Channel.type&#x60;. Defaults applied by the platform exclude DMs; passing this overrides.  | [Optional] |

### Return type

[**ListChannelsResponse**](ListChannelsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Channel list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## sendChannelMessage

> SendChatMessageResponse sendChannelMessage(sendChatMessageRequest)

Send a message to a channel.

### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { SendChannelMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // SendChatMessageRequest
    sendChatMessageRequest: ...,
  } satisfies SendChannelMessageRequest;

  try {
    const data = await api.sendChannelMessage(body);
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
| **sendChatMessageRequest** | [SendChatMessageRequest](SendChatMessageRequest.md) |  | |

### Return type

[**SendChatMessageResponse**](SendChatMessageResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Send result. |  -  |
| **400** | Invalid body or missing channel. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateChannel

> { [key: string]: any; } workspaceCreateChannel(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceCreateChannelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateChannelRequest;

  try {
    const data = await api.workspaceCreateChannel(body);
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


## workspaceExecuteChannelAction

> { [key: string]: any; } workspaceExecuteChannelAction(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceExecuteChannelActionRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceExecuteChannelActionRequest;

  try {
    const data = await api.workspaceExecuteChannelAction(body);
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
| **200** | Result |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceJoinChannel

> workspaceJoinChannel(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceJoinChannelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; } (optional)
    requestBody: Object,
  } satisfies WorkspaceJoinChannelRequest;

  try {
    const data = await api.workspaceJoinChannel(body);
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
| **requestBody** | `{ [key: string]: any; }` |  | [Optional] |

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
| **204** | Joined |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceLeaveChannel

> workspaceLeaveChannel(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceLeaveChannelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; } (optional)
    requestBody: Object,
  } satisfies WorkspaceLeaveChannelRequest;

  try {
    const data = await api.workspaceLeaveChannel(body);
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
| **requestBody** | `{ [key: string]: any; }` |  | [Optional] |

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
| **204** | Left |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListChannelActions

> { [key: string]: any; } workspaceListChannelActions(org, workspace)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListChannelActionsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListChannelActionsRequest;

  try {
    const data = await api.workspaceListChannelActions(body);
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
| **200** | Actions |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListChannelMessages

> { [key: string]: any; } workspaceListChannelMessages(org, workspace)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListChannelMessagesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListChannelMessagesRequest;

  try {
    const data = await api.workspaceListChannelMessages(body);
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
| **200** | Messages |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListChannels

> { [key: string]: any; } workspaceListChannels(org, workspace)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListChannelsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListChannelsRequest;

  try {
    const data = await api.workspaceListChannels(body);
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
| **200** | Channels |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceSendChannelMessage

> { [key: string]: any; } workspaceSendChannelMessage(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  ChannelsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceSendChannelMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ChannelsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceSendChannelMessageRequest;

  try {
    const data = await api.workspaceSendChannelMessage(body);
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
| **200** | Sent |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

