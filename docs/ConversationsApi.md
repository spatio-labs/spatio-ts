# ConversationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createConversation**](ConversationsApi.md#createconversationoperation) | **POST** /v1/conversations | Persist a new LLM conversation. |
| [**deleteConversation**](ConversationsApi.md#deleteconversation) | **DELETE** /v1/conversations/{id} | Soft-delete a conversation. |
| [**getConversation**](ConversationsApi.md#getconversation) | **GET** /v1/conversations/{id} | Fetch one conversation. |
| [**getLatestConversationForContext**](ConversationsApi.md#getlatestconversationforcontext) | **GET** /v1/conversations/latest | Fetch the most recently active conversation for a given context tag. |
| [**listConversationMessages**](ConversationsApi.md#listconversationmessages) | **GET** /v1/conversations/{id}/messages | List messages in a conversation. |
| [**listConversations**](ConversationsApi.md#listconversations) | **GET** /v1/conversations | List the caller\&#39;s persisted LLM conversations. |
| [**saveConversationMessage**](ConversationsApi.md#saveconversationmessage) | **POST** /v1/conversations/{id}/messages | Append a message to a conversation. |
| [**updateConversation**](ConversationsApi.md#updateconversationoperation) | **PATCH** /v1/conversations/{id} | Update conversation metadata (title, context, cwd, session_id, pinned). |
| [**updateConversationMessageMetadata**](ConversationsApi.md#updateconversationmessagemetadata) | **PATCH** /v1/conversations/{id}/messages | Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message).  |



## createConversation

> Conversation createConversation(createConversationRequest)

Persist a new LLM conversation.

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateConversationOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // CreateConversationRequest (optional)
    createConversationRequest: ...,
  } satisfies CreateConversationOperationRequest;

  try {
    const data = await api.createConversation(body);
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
| **createConversationRequest** | [CreateConversationRequest](CreateConversationRequest.md) |  | [Optional] |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created conversation. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteConversation

> deleteConversation(id)

Soft-delete a conversation.

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteConversationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteConversationRequest;

  try {
    const data = await api.deleteConversation(body);
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


## getConversation

> Conversation getConversation(id)

Fetch one conversation.

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { GetConversationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetConversationRequest;

  try {
    const data = await api.getConversation(body);
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

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversation. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Conversation not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getLatestConversationForContext

> Conversation getLatestConversationForContext(context)

Fetch the most recently active conversation for a given context tag.

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { GetLatestConversationForContextRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string
    context: context_example,
  } satisfies GetLatestConversationForContextRequest;

  try {
    const data = await api.getLatestConversationForContext(body);
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
| **context** | `string` |  | [Defaults to `undefined`] |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The matching conversation, if any. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | No conversation found for that context. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listConversationMessages

> Array&lt;ConversationMessage&gt; listConversationMessages(id, limit, before)

List messages in a conversation.

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { ListConversationMessagesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string
    id: id_example,
    // number (optional)
    limit: 56,
    // string (optional)
    before: before_example,
  } satisfies ListConversationMessagesRequest;

  try {
    const data = await api.listConversationMessages(body);
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
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |
| **before** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**Array&lt;ConversationMessage&gt;**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message list (bare array). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listConversations

> Array&lt;Conversation&gt; listConversations(context, limit)

List the caller\&#39;s persisted LLM conversations.

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { ListConversationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string (optional)
    context: context_example,
    // number (optional)
    limit: 56,
  } satisfies ListConversationsRequest;

  try {
    const data = await api.listConversations(body);
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
| **context** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**Array&lt;Conversation&gt;**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversation list (bare array — no envelope). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## saveConversationMessage

> ConversationMessage saveConversationMessage(id, saveMessageRequest)

Append a message to a conversation.

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { SaveConversationMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string
    id: id_example,
    // SaveMessageRequest
    saveMessageRequest: ...,
  } satisfies SaveConversationMessageRequest;

  try {
    const data = await api.saveConversationMessage(body);
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
| **saveMessageRequest** | [SaveMessageRequest](SaveMessageRequest.md) |  | |

### Return type

[**ConversationMessage**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Saved message. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateConversation

> Conversation updateConversation(id, updateConversationRequest)

Update conversation metadata (title, context, cwd, session_id, pinned).

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateConversationOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateConversationRequest
    updateConversationRequest: ...,
  } satisfies UpdateConversationOperationRequest;

  try {
    const data = await api.updateConversation(body);
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
| **updateConversationRequest** | [UpdateConversationRequest](UpdateConversationRequest.md) |  | |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated conversation. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateConversationMessageMetadata

> ConversationMessage updateConversationMessageMetadata(id, updateMessageMetadataRequest)

Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). 

### Example

```ts
import {
  Configuration,
  ConversationsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateConversationMessageMetadataRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ConversationsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateMessageMetadataRequest
    updateMessageMetadataRequest: ...,
  } satisfies UpdateConversationMessageMetadataRequest;

  try {
    const data = await api.updateConversationMessageMetadata(body);
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
| **updateMessageMetadataRequest** | [UpdateMessageMetadataRequest](UpdateMessageMetadataRequest.md) |  | |

### Return type

[**ConversationMessage**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated message. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

