# DirectMessagesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addDMReaction**](DirectMessagesApi.md#adddmreaction) | **POST** /v1/direct-messages/messages/{messageId}/reactions | React to a DM message. |
| [**attachToDMMessage**](DirectMessagesApi.md#attachtodmmessage) | **POST** /v1/direct-messages/messages/{messageId}/attachments | Attach a file/image/etc. to an existing DM message. |
| [**executeDMAction**](DirectMessagesApi.md#executedmaction) | **POST** /v1/direct-messages/execute | Dispatch a DM action by id. |
| [**forwardDMMessage**](DirectMessagesApi.md#forwarddmmessage) | **POST** /v1/direct-messages/messages/{messageId}/forward | Forward a DM message to another DM or channel. |
| [**getDMUser**](DirectMessagesApi.md#getdmuser) | **GET** /v1/direct-messages/users/{id} | Fetch one chat user. |
| [**listDMActions**](DirectMessagesApi.md#listdmactions) | **GET** /v1/direct-messages/actions | Discover the action catalog for DirectMessages. |
| [**listDMPinnedMessages**](DirectMessagesApi.md#listdmpinnedmessages) | **GET** /v1/direct-messages/{dmId}/pinned | List pinned messages in a DM conversation. |
| [**listDMThreadReplies**](DirectMessagesApi.md#listdmthreadreplies) | **GET** /v1/direct-messages/{dmId}/messages/{messageId}/replies | List replies in a DM message thread. |
| [**listDMUsers**](DirectMessagesApi.md#listdmusers) | **GET** /v1/direct-messages/users | List chat users (DM contacts) across connected accounts. |
| [**listDirectConversationsEnriched**](DirectMessagesApi.md#listdirectconversationsenriched) | **GET** /v1/direct-messages/conversations | Enriched DM conversation list with unread + pin + draft state. |
| [**listDirectMessageConversations**](DirectMessagesApi.md#listdirectmessageconversations) | **GET** /v1/direct-messages | List 1:1 and group DM conversations. |
| [**listDirectMessages**](DirectMessagesApi.md#listdirectmessages) | **GET** /v1/direct-messages/messages | List messages in a DM conversation. |
| [**markDMRead**](DirectMessagesApi.md#markdmread) | **POST** /v1/direct-messages/{dmId}/read | Mark a DM message read. |
| [**muteDM**](DirectMessagesApi.md#mutedm) | **POST** /v1/direct-messages/{dmId}/mute | Mute a DM conversation (until a time, or forever). |
| [**pinDMConversation**](DirectMessagesApi.md#pindmconversation) | **POST** /v1/direct-messages/{dmId}/pin | Pin a DM conversation to the top of the sidebar. |
| [**pinDMMessage**](DirectMessagesApi.md#pindmmessage) | **POST** /v1/direct-messages/messages/{messageId}/pin | Pin a DM message. |
| [**postDMThreadReply**](DirectMessagesApi.md#postdmthreadreply) | **POST** /v1/direct-messages/{dmId}/messages/{messageId}/replies | Reply in a DM message thread. |
| [**removeDMReaction**](DirectMessagesApi.md#removedmreaction) | **DELETE** /v1/direct-messages/messages/{messageId}/reactions/{emoji} | Remove a DM message reaction. |
| [**searchDirectMessages**](DirectMessagesApi.md#searchdirectmessages) | **GET** /v1/direct-messages/search | Search across DM messages. |
| [**sendDirectMessage**](DirectMessagesApi.md#senddirectmessage) | **POST** /v1/direct-messages/messages | Send a DM. |
| [**setDMDraft**](DirectMessagesApi.md#setdmdraft) | **PUT** /v1/direct-messages/{dmId}/draft | Save the unsent draft text for a DM. |
| [**unpinDMConversation**](DirectMessagesApi.md#unpindmconversation) | **DELETE** /v1/direct-messages/{dmId}/pin | Unpin a DM conversation. |
| [**unpinDMMessage**](DirectMessagesApi.md#unpindmmessage) | **DELETE** /v1/direct-messages/messages/{messageId}/pin | Unpin a DM message. |
| [**workspaceExecuteDMAction**](DirectMessagesApi.md#workspaceexecutedmaction) | **POST** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/execute |  |
| [**workspaceGetDMUser**](DirectMessagesApi.md#workspacegetdmuser) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/users/{id} |  |
| [**workspaceListDMActions**](DirectMessagesApi.md#workspacelistdmactions) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/actions |  |
| [**workspaceListDMConversations**](DirectMessagesApi.md#workspacelistdmconversations) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/conversations |  |
| [**workspaceListDMMessages**](DirectMessagesApi.md#workspacelistdmmessages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/messages |  |
| [**workspaceListDMUsers**](DirectMessagesApi.md#workspacelistdmusers) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/users |  |
| [**workspaceListDirectMessages**](DirectMessagesApi.md#workspacelistdirectmessages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages |  |
| [**workspaceSendDirectMessage**](DirectMessagesApi.md#workspacesenddirectmessage) | **POST** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/messages |  |



## addDMReaction

> DMReactionResponse addDMReaction(messageId, dMReactionRequest)

React to a DM message.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { AddDMReactionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Chat-message id.
    messageId: messageId_example,
    // DMReactionRequest
    dMReactionRequest: ...,
  } satisfies AddDMReactionRequest;

  try {
    const data = await api.addDMReaction(body);
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
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
| **dMReactionRequest** | [DMReactionRequest](DMReactionRequest.md) |  | |

### Return type

[**DMReactionResponse**](DMReactionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated reactions. |  -  |
| **400** | Invalid body or missing emoji. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## attachToDMMessage

> DMMessageEnvelope attachToDMMessage(messageId, dMAttachRequest)

Attach a file/image/etc. to an existing DM message.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { AttachToDMMessageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Chat-message id.
    messageId: messageId_example,
    // DMAttachRequest
    dMAttachRequest: ...,
  } satisfies AttachToDMMessageRequest;

  try {
    const data = await api.attachToDMMessage(body);
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
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
| **dMAttachRequest** | [DMAttachRequest](DMAttachRequest.md) |  | |

### Return type

[**DMMessageEnvelope**](DMMessageEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated message envelope. |  -  |
| **400** | Invalid body or missing fields. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## executeDMAction

> ExecuteChatActionResponse executeDMAction(executeChatActionRequest)

Dispatch a DM action by id.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ExecuteDMActionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // ExecuteChatActionRequest
    executeChatActionRequest: ...,
  } satisfies ExecuteDMActionRequest;

  try {
    const data = await api.executeDMAction(body);
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


## forwardDMMessage

> DMMessageEnvelope forwardDMMessage(messageId, dMForwardRequest)

Forward a DM message to another DM or channel.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ForwardDMMessageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Chat-message id.
    messageId: messageId_example,
    // DMForwardRequest
    dMForwardRequest: ...,
  } satisfies ForwardDMMessageRequest;

  try {
    const data = await api.forwardDMMessage(body);
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
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
| **dMForwardRequest** | [DMForwardRequest](DMForwardRequest.md) |  | |

### Return type

[**DMMessageEnvelope**](DMMessageEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Forwarded message envelope. |  -  |
| **400** | Invalid body or missing destination. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getDMUser

> GetChatUserResponse getDMUser(id, accountId)

Fetch one chat user.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { GetDMUserRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Chat-user id (provider-scoped).
    id: id_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies GetDMUserRequest;

  try {
    const data = await api.getDMUser(body);
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
| **id** | `string` | Chat-user id (provider-scoped). | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**GetChatUserResponse**](GetChatUserResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The user. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | User not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDMActions

> ChatActionsList listDMActions()

Discover the action catalog for DirectMessages.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ListDMActionsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  try {
    const data = await api.listDMActions();
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


## listDMPinnedMessages

> DMPinnedList listDMPinnedMessages(dmId, accountId)

List pinned messages in a DM conversation.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ListDMPinnedMessagesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies ListDMPinnedMessagesRequest;

  try {
    const data = await api.listDMPinnedMessages(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**DMPinnedList**](DMPinnedList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pinned-message list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDMThreadReplies

> { [key: string]: any; } listDMThreadReplies(dmId, messageId, accountId)

List replies in a DM message thread.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ListDMThreadRepliesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // string | Chat-message id.
    messageId: messageId_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies ListDMThreadRepliesRequest;

  try {
    const data = await api.listDMThreadReplies(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Thread replies. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDMUsers

> ListChatUsersResponse listDMUsers(accountIds, providers, xWorkspaceID, limit, cursor)

List chat users (DM contacts) across connected accounts.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ListDMUsersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
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
  } satisfies ListDMUsersRequest;

  try {
    const data = await api.listDMUsers(body);
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
| **cursor** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**ListChatUsersResponse**](ListChatUsersResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDirectConversationsEnriched

> { [key: string]: any; } listDirectConversationsEnriched(accountId, xWorkspaceID)

Enriched DM conversation list with unread + pin + draft state.

Native fast-path. Returns conversations augmented with the DM-feature state (unread counts, pinned/muted flags, saved drafts) the renderer\&#39;s DM UI consumes. The shape is provider-specific and treated as opaque. 

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ListDirectConversationsEnrichedRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies ListDirectConversationsEnrichedRequest;

  try {
    const data = await api.listDirectConversationsEnriched(body);
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
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

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
| **200** | Enriched conversation list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDirectMessageConversations

> ListChannelsResponse listDirectMessageConversations(accountIds, providers, xWorkspaceID, limit, cursor, includeArchived)

List 1:1 and group DM conversations.

Returns DM-type conversations only (&#x60;type: im | mpim&#x60;). Channel-type conversations are surfaced via &#x60;/v1/channels&#x60;. 

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ListDirectMessageConversationsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
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
    includeArchived: true,
  } satisfies ListDirectMessageConversationsRequest;

  try {
    const data = await api.listDirectMessageConversations(body);
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
| **cursor** | `string` |  | [Optional] [Defaults to `undefined`] |
| **includeArchived** | `boolean` |  | [Optional] [Defaults to `false`] |

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
| **200** | DM conversation list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDirectMessages

> ListMessagesResponse listDirectMessages(channel, accountId, accountIds, providers, xWorkspaceID, limit, cursor, oldestFirst)

List messages in a DM conversation.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { ListDirectMessagesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | DM conversation id.
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
  } satisfies ListDirectMessagesRequest;

  try {
    const data = await api.listDirectMessages(body);
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
| **channel** | `string` | DM conversation id. | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |
| **accountIds** | `Array<string>` | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [Optional] |
| **providers** | `Array<string>` | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [Optional] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |
| **cursor** | `string` |  | [Optional] [Defaults to `undefined`] |
| **oldestFirst** | `boolean` |  | [Optional] [Defaults to `undefined`] |

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


## markDMRead

> SuccessFlag markDMRead(dmId, dMMarkReadRequest)

Mark a DM message read.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { MarkDMReadRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // DMMarkReadRequest
    dMMarkReadRequest: ...,
  } satisfies MarkDMReadRequest;

  try {
    const data = await api.markDMRead(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **dMMarkReadRequest** | [DMMarkReadRequest](DMMarkReadRequest.md) |  | |

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
| **400** | Missing body or messageId. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## muteDM

> DMMuteResponse muteDM(dmId, dMMuteRequest)

Mute a DM conversation (until a time, or forever).

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { MuteDMRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // DMMuteRequest
    dMMuteRequest: ...,
  } satisfies MuteDMRequest;

  try {
    const data = await api.muteDM(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **dMMuteRequest** | [DMMuteRequest](DMMuteRequest.md) |  | |

### Return type

[**DMMuteResponse**](DMMuteResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mute applied. |  -  |
| **400** | Invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## pinDMConversation

> SuccessFlag pinDMConversation(dmId, accountId)

Pin a DM conversation to the top of the sidebar.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { PinDMConversationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies PinDMConversationRequest;

  try {
    const data = await api.pinDMConversation(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

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

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## pinDMMessage

> SuccessFlag pinDMMessage(messageId, channelMembershipRequest)

Pin a DM message.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { PinDMMessageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Chat-message id.
    messageId: messageId_example,
    // ChannelMembershipRequest (optional)
    channelMembershipRequest: ...,
  } satisfies PinDMMessageRequest;

  try {
    const data = await api.pinDMMessage(body);
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
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
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
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## postDMThreadReply

> DMMessageEnvelope postDMThreadReply(dmId, messageId, dMThreadReplyRequest, accountId)

Reply in a DM message thread.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { PostDMThreadReplyRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // string | Chat-message id.
    messageId: messageId_example,
    // DMThreadReplyRequest
    dMThreadReplyRequest: ...,
    // string (optional)
    accountId: accountId_example,
  } satisfies PostDMThreadReplyRequest;

  try {
    const data = await api.postDMThreadReply(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
| **dMThreadReplyRequest** | [DMThreadReplyRequest](DMThreadReplyRequest.md) |  | |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**DMMessageEnvelope**](DMMessageEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reply created. |  -  |
| **400** | Invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## removeDMReaction

> DMReactionResponse removeDMReaction(messageId, emoji, accountId)

Remove a DM message reaction.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { RemoveDMReactionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Chat-message id.
    messageId: messageId_example,
    // string | Reaction emoji (e.g. `+1`, `eyes`, `pepper`).
    emoji: emoji_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies RemoveDMReactionRequest;

  try {
    const data = await api.removeDMReaction(body);
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
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
| **emoji** | `string` | Reaction emoji (e.g. &#x60;+1&#x60;, &#x60;eyes&#x60;, &#x60;pepper&#x60;). | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**DMReactionResponse**](DMReactionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated reactions. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchDirectMessages

> DMSearchResults searchDirectMessages(q, limit, dmId, user, accountId)

Search across DM messages.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { SearchDirectMessagesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Free-form query string.
    q: q_example,
    // number (optional)
    limit: 56,
    // string | Restrict to one conversation. (optional)
    dmId: dmId_example,
    // string | Restrict to messages from this user id. (optional)
    user: user_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies SearchDirectMessagesRequest;

  try {
    const data = await api.searchDirectMessages(body);
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
| **q** | `string` | Free-form query string. | [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |
| **dmId** | `string` | Restrict to one conversation. | [Optional] [Defaults to `undefined`] |
| **user** | `string` | Restrict to messages from this user id. | [Optional] [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**DMSearchResults**](DMSearchResults.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results (provider-shaped). |  -  |
| **400** | Missing query. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## sendDirectMessage

> SendChatMessageResponse sendDirectMessage(sendChatMessageRequest)

Send a DM.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { SendDirectMessageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // SendChatMessageRequest
    sendChatMessageRequest: ...,
  } satisfies SendDirectMessageRequest;

  try {
    const data = await api.sendDirectMessage(body);
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


## setDMDraft

> SuccessFlag setDMDraft(dmId, dMSetDraftRequest)

Save the unsent draft text for a DM.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { SetDMDraftRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // DMSetDraftRequest
    dMSetDraftRequest: ...,
  } satisfies SetDMDraftRequest;

  try {
    const data = await api.setDMDraft(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **dMSetDraftRequest** | [DMSetDraftRequest](DMSetDraftRequest.md) |  | |

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
| **400** | Invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## unpinDMConversation

> SuccessFlag unpinDMConversation(dmId, accountId)

Unpin a DM conversation.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { UnpinDMConversationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Direct-message conversation id.
    dmId: dmId_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies UnpinDMConversationRequest;

  try {
    const data = await api.unpinDMConversation(body);
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
| **dmId** | `string` | Direct-message conversation id. | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

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

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## unpinDMMessage

> SuccessFlag unpinDMMessage(messageId, accountId)

Unpin a DM message.

### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { UnpinDMMessageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string | Chat-message id.
    messageId: messageId_example,
    // string (optional)
    accountId: accountId_example,
  } satisfies UnpinDMMessageRequest;

  try {
    const data = await api.unpinDMMessage(body);
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
| **messageId** | `string` | Chat-message id. | [Defaults to `undefined`] |
| **accountId** | `string` |  | [Optional] [Defaults to `undefined`] |

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

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceExecuteDMAction

> { [key: string]: any; } workspaceExecuteDMAction(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceExecuteDMActionRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceExecuteDMActionRequest;

  try {
    const data = await api.workspaceExecuteDMAction(body);
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


## workspaceGetDMUser

> { [key: string]: any; } workspaceGetDMUser(org, workspace, id)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetDMUserRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetDMUserRequest;

  try {
    const data = await api.workspaceGetDMUser(body);
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
| **200** | User |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListDMActions

> { [key: string]: any; } workspaceListDMActions(org, workspace)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListDMActionsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListDMActionsRequest;

  try {
    const data = await api.workspaceListDMActions(body);
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


## workspaceListDMConversations

> { [key: string]: any; } workspaceListDMConversations(org, workspace)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListDMConversationsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListDMConversationsRequest;

  try {
    const data = await api.workspaceListDMConversations(body);
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
| **200** | Conversations |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListDMMessages

> { [key: string]: any; } workspaceListDMMessages(org, workspace)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListDMMessagesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListDMMessagesRequest;

  try {
    const data = await api.workspaceListDMMessages(body);
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


## workspaceListDMUsers

> { [key: string]: any; } workspaceListDMUsers(org, workspace)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListDMUsersRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListDMUsersRequest;

  try {
    const data = await api.workspaceListDMUsers(body);
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
| **200** | Users |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListDirectMessages

> { [key: string]: any; } workspaceListDirectMessages(org, workspace)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListDirectMessagesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListDirectMessagesRequest;

  try {
    const data = await api.workspaceListDirectMessages(body);
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
| **200** | DMs |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceSendDirectMessage

> { [key: string]: any; } workspaceSendDirectMessage(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  DirectMessagesApi,
} from '@spatio/sdk-ts';
import type { WorkspaceSendDirectMessageRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DirectMessagesApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceSendDirectMessageRequest;

  try {
    const data = await api.workspaceSendDirectMessage(body);
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

