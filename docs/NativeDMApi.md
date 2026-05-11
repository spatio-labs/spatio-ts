# NativeDMApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addNativeDMReaction**](NativeDMApi.md#addnativedmreaction) | **POST** /v1/native/dm/messages/{messageId}/reactions | Add a reaction to a DM message. |
| [**attachToNativeDMMessage**](NativeDMApi.md#attachtonativedmmessage) | **POST** /v1/native/dm/messages/{messageId}/attachments | Attach a file to a DM message. |
| [**deleteNativeDMMessage**](NativeDMApi.md#deletenativedmmessage) | **DELETE** /v1/native/dm/{dmId}/messages/{messageId} | Delete a DM message. |
| [**forwardNativeDMMessage**](NativeDMApi.md#forwardnativedmmessage) | **POST** /v1/native/dm/messages/{messageId}/forward | Forward a DM message to another conversation. |
| [**listNativeDMChannels**](NativeDMApi.md#listnativedmchannels) | **GET** /v1/native/dm | List the caller\&#39;s DM channels. |
| [**listNativeDMConversations**](NativeDMApi.md#listnativedmconversations) | **GET** /v1/native/dm/conversations | List DM conversations with metadata (last message, unread count, etc.). |
| [**listNativeDMMessages**](NativeDMApi.md#listnativedmmessages) | **GET** /v1/native/dm/{dmId}/messages | List messages in a DM. |
| [**listNativeDMPinnedMessages**](NativeDMApi.md#listnativedmpinnedmessages) | **GET** /v1/native/dm/{dmId}/pinned | List pinned messages in a DM. |
| [**listNativeDMThreadReplies**](NativeDMApi.md#listnativedmthreadreplies) | **GET** /v1/native/dm/{dmId}/messages/{messageId}/replies | List threaded replies on a message. |
| [**markNativeDMRead**](NativeDMApi.md#marknativedmread) | **POST** /v1/native/dm/{dmId}/read | Mark a DM as read. |
| [**muteNativeDM**](NativeDMApi.md#mutenativedm) | **POST** /v1/native/dm/{dmId}/mute | Mute a DM. |
| [**pinNativeDMConversation**](NativeDMApi.md#pinnativedmconversation) | **POST** /v1/native/dm/{dmId}/pin | Pin a DM conversation in the sidebar. |
| [**pinNativeDMMessage**](NativeDMApi.md#pinnativedmmessage) | **POST** /v1/native/dm/messages/{messageId}/pin | Pin a DM message. |
| [**postNativeDMMessage**](NativeDMApi.md#postnativedmmessage) | **POST** /v1/native/dm | Post a DM message (top-level entry). |
| [**postNativeDMThreadReply**](NativeDMApi.md#postnativedmthreadreply) | **POST** /v1/native/dm/{dmId}/messages/{messageId}/replies | Post a threaded reply. |
| [**removeNativeDMReaction**](NativeDMApi.md#removenativedmreaction) | **DELETE** /v1/native/dm/messages/{messageId}/reactions/{emoji} | Remove a reaction. |
| [**searchNativeDMMessages**](NativeDMApi.md#searchnativedmmessages) | **GET** /v1/native/dm/search | Search DM messages. |
| [**setNativeDMDraft**](NativeDMApi.md#setnativedmdraft) | **PUT** /v1/native/dm/{dmId}/draft | Save a draft on a DM conversation. |
| [**unpinNativeDMConversation**](NativeDMApi.md#unpinnativedmconversation) | **DELETE** /v1/native/dm/{dmId}/pin | Unpin a DM conversation. |
| [**unpinNativeDMMessage**](NativeDMApi.md#unpinnativedmmessage) | **DELETE** /v1/native/dm/messages/{messageId}/pin | Unpin a DM message. |
| [**updateNativeDMMessage**](NativeDMApi.md#updatenativedmmessage) | **PATCH** /v1/native/dm/{dmId}/messages/{messageId} | Update a DM message body. |



## addNativeDMReaction

> { [key: string]: any; } addNativeDMReaction(messageId, requestBody)

Add a reaction to a DM message.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { AddNativeDMReactionRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    messageId: messageId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies AddNativeDMReactionRequest;

  try {
    const data = await api.addNativeDMReaction(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Added. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## attachToNativeDMMessage

> { [key: string]: any; } attachToNativeDMMessage(messageId, requestBody)

Attach a file to a DM message.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { AttachToNativeDMMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    messageId: messageId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies AttachToNativeDMMessageRequest;

  try {
    const data = await api.attachToNativeDMMessage(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Attached. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteNativeDMMessage

> deleteNativeDMMessage(dmId, messageId)

Delete a DM message.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteNativeDMMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
    // string
    messageId: messageId_example,
  } satisfies DeleteNativeDMMessageRequest;

  try {
    const data = await api.deleteNativeDMMessage(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |
| **messageId** | `string` |  | [Defaults to `undefined`] |

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


## forwardNativeDMMessage

> { [key: string]: any; } forwardNativeDMMessage(messageId, requestBody)

Forward a DM message to another conversation.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { ForwardNativeDMMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    messageId: messageId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies ForwardNativeDMMessageRequest;

  try {
    const data = await api.forwardNativeDMMessage(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Forwarded. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNativeDMChannels

> { [key: string]: any; } listNativeDMChannels()

List the caller\&#39;s DM channels.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { ListNativeDMChannelsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  try {
    const data = await api.listNativeDMChannels();
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | DM list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNativeDMConversations

> { [key: string]: any; } listNativeDMConversations()

List DM conversations with metadata (last message, unread count, etc.).

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { ListNativeDMConversationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  try {
    const data = await api.listNativeDMConversations();
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversations. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNativeDMMessages

> { [key: string]: any; } listNativeDMMessages(dmId)

List messages in a DM.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { ListNativeDMMessagesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
  } satisfies ListNativeDMMessagesRequest;

  try {
    const data = await api.listNativeDMMessages(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Messages. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNativeDMPinnedMessages

> { [key: string]: any; } listNativeDMPinnedMessages(dmId)

List pinned messages in a DM.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { ListNativeDMPinnedMessagesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
  } satisfies ListNativeDMPinnedMessagesRequest;

  try {
    const data = await api.listNativeDMPinnedMessages(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Pinned messages. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNativeDMThreadReplies

> { [key: string]: any; } listNativeDMThreadReplies(dmId, messageId)

List threaded replies on a message.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { ListNativeDMThreadRepliesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
    // string
    messageId: messageId_example,
  } satisfies ListNativeDMThreadRepliesRequest;

  try {
    const data = await api.listNativeDMThreadReplies(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |
| **messageId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Replies. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## markNativeDMRead

> markNativeDMRead(dmId)

Mark a DM as read.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { MarkNativeDMReadRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
  } satisfies MarkNativeDMReadRequest;

  try {
    const data = await api.markNativeDMRead(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Marked read. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## muteNativeDM

> muteNativeDM(dmId, requestBody)

Mute a DM.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { MuteNativeDMRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
    // { [key: string]: any; } (optional)
    requestBody: Object,
  } satisfies MuteNativeDMRequest;

  try {
    const data = await api.muteNativeDM(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |
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
| **204** | Muted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## pinNativeDMConversation

> pinNativeDMConversation(dmId)

Pin a DM conversation in the sidebar.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { PinNativeDMConversationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
  } satisfies PinNativeDMConversationRequest;

  try {
    const data = await api.pinNativeDMConversation(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Pinned. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## pinNativeDMMessage

> pinNativeDMMessage(messageId)

Pin a DM message.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { PinNativeDMMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    messageId: messageId_example,
  } satisfies PinNativeDMMessageRequest;

  try {
    const data = await api.pinNativeDMMessage(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Pinned. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## postNativeDMMessage

> { [key: string]: any; } postNativeDMMessage(requestBody)

Post a DM message (top-level entry).

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { PostNativeDMMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PostNativeDMMessageRequest;

  try {
    const data = await api.postNativeDMMessage(body);
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
| **200** | Posted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## postNativeDMThreadReply

> { [key: string]: any; } postNativeDMThreadReply(dmId, messageId, requestBody)

Post a threaded reply.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { PostNativeDMThreadReplyRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
    // string
    messageId: messageId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies PostNativeDMThreadReplyRequest;

  try {
    const data = await api.postNativeDMThreadReply(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |
| **messageId** | `string` |  | [Defaults to `undefined`] |
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
| **201** | Posted. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## removeNativeDMReaction

> removeNativeDMReaction(messageId, emoji)

Remove a reaction.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { RemoveNativeDMReactionRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    messageId: messageId_example,
    // string
    emoji: emoji_example,
  } satisfies RemoveNativeDMReactionRequest;

  try {
    const data = await api.removeNativeDMReaction(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |
| **emoji** | `string` |  | [Defaults to `undefined`] |

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


## searchNativeDMMessages

> { [key: string]: any; } searchNativeDMMessages(q)

Search DM messages.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { SearchNativeDMMessagesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string (optional)
    q: q_example,
  } satisfies SearchNativeDMMessagesRequest;

  try {
    const data = await api.searchNativeDMMessages(body);
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
| **q** | `string` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Search results. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setNativeDMDraft

> setNativeDMDraft(dmId, requestBody)

Save a draft on a DM conversation.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { SetNativeDMDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies SetNativeDMDraftRequest;

  try {
    const data = await api.setNativeDMDraft(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` |  | |

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
| **204** | Saved. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## unpinNativeDMConversation

> unpinNativeDMConversation(dmId)

Unpin a DM conversation.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { UnpinNativeDMConversationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
  } satisfies UnpinNativeDMConversationRequest;

  try {
    const data = await api.unpinNativeDMConversation(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Unpinned. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## unpinNativeDMMessage

> unpinNativeDMMessage(messageId)

Unpin a DM message.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { UnpinNativeDMMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    messageId: messageId_example,
  } satisfies UnpinNativeDMMessageRequest;

  try {
    const data = await api.unpinNativeDMMessage(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Unpinned. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateNativeDMMessage

> { [key: string]: any; } updateNativeDMMessage(dmId, messageId, requestBody)

Update a DM message body.

### Example

```ts
import {
  Configuration,
  NativeDMApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateNativeDMMessageRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new NativeDMApi(config);

  const body = {
    // string
    dmId: dmId_example,
    // string
    messageId: messageId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies UpdateNativeDMMessageRequest;

  try {
    const data = await api.updateNativeDMMessage(body);
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
| **dmId** | `string` |  | [Defaults to `undefined`] |
| **messageId** | `string` |  | [Defaults to `undefined`] |
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

