# AgentsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAgent**](AgentsApi.md#createagentoperation) | **POST** /v1/agents | Create a new agent configuration. |
| [**createAgentConversation**](AgentsApi.md#createagentconversationoperation) | **POST** /v1/agent/conversations | Create a new agent-platform conversation. |
| [**createAgentMessage**](AgentsApi.md#createagentmessageoperation) | **POST** /v1/agent/conversations/{id}/messages | Append a message to an agent conversation. |
| [**deleteAgent**](AgentsApi.md#deleteagent) | **DELETE** /v1/agents/{id} | Delete an agent configuration. |
| [**executeAgentAction**](AgentsApi.md#executeagentaction) | **POST** /v1/agent/actions/execute | Execute an action through the agent platform. |
| [**getAgent**](AgentsApi.md#getagent) | **GET** /v1/agents/{id} | Fetch one agent configuration. |
| [**getAgentConversation**](AgentsApi.md#getagentconversation) | **GET** /v1/agent/conversations/{id} | Fetch one agent conversation. |
| [**getAgentSessionContext**](AgentsApi.md#getagentsessioncontext) | **GET** /v1/agent/session-context | Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn\&#39;t fish on its first turn.  |
| [**listAgentConversationMessages**](AgentsApi.md#listagentconversationmessages) | **GET** /v1/agent/conversations/{id}/messages | List messages on an agent conversation. |
| [**listAgentConversations**](AgentsApi.md#listagentconversations) | **GET** /v1/agent/conversations | List the caller\&#39;s agent-platform conversations. Distinct from &#x60;/v1/conversations&#x60; (renderer-driven sidebar persistence).  |
| [**listAgents**](AgentsApi.md#listagents) | **GET** /v1/agents | List the caller\&#39;s agent configurations. |
| [**listPreconfiguredAgents**](AgentsApi.md#listpreconfiguredagents) | **GET** /v1/agents/preconfigured | Curated featured agents (e.g. \&quot;Claude Code\&quot;, \&quot;Research Assistant\&quot;). Read-only — these are surfaced by the renderer\&#39;s preconfigured-picker UI.  |
| [**updateAgent**](AgentsApi.md#updateagentoperation) | **PATCH** /v1/agents/{id} | Update an agent configuration. |



## createAgent

> Agent createAgent(createAgentRequest)

Create a new agent configuration.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateAgentOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // CreateAgentRequest
    createAgentRequest: ...,
  } satisfies CreateAgentOperationRequest;

  try {
    const data = await api.createAgent(body);
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
| **createAgentRequest** | [CreateAgentRequest](CreateAgentRequest.md) |  | |

### Return type

[**Agent**](Agent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created agent. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createAgentConversation

> AgentConversation createAgentConversation(createAgentConversationRequest)

Create a new agent-platform conversation.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateAgentConversationOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // CreateAgentConversationRequest (optional)
    createAgentConversationRequest: ...,
  } satisfies CreateAgentConversationOperationRequest;

  try {
    const data = await api.createAgentConversation(body);
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
| **createAgentConversationRequest** | [CreateAgentConversationRequest](CreateAgentConversationRequest.md) |  | [Optional] |

### Return type

[**AgentConversation**](AgentConversation.md)

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


## createAgentMessage

> AgentMessage createAgentMessage(id, createAgentMessageRequest)

Append a message to an agent conversation.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateAgentMessageOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // string
    id: id_example,
    // CreateAgentMessageRequest
    createAgentMessageRequest: ...,
  } satisfies CreateAgentMessageOperationRequest;

  try {
    const data = await api.createAgentMessage(body);
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
| **createAgentMessageRequest** | [CreateAgentMessageRequest](CreateAgentMessageRequest.md) |  | |

### Return type

[**AgentMessage**](AgentMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created message. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAgent

> deleteAgent(id)

Delete an agent configuration.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteAgentRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteAgentRequest;

  try {
    const data = await api.deleteAgent(body);
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


## executeAgentAction

> ExecuteActionResponse executeAgentAction(executeActionRequest)

Execute an action through the agent platform.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { ExecuteAgentActionRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // ExecuteActionRequest
    executeActionRequest: ...,
  } satisfies ExecuteAgentActionRequest;

  try {
    const data = await api.executeAgentAction(body);
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
| **executeActionRequest** | [ExecuteActionRequest](ExecuteActionRequest.md) |  | |

### Return type

[**ExecuteActionResponse**](ExecuteActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Execution result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAgent

> Agent getAgent(id)

Fetch one agent configuration.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { GetAgentRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetAgentRequest;

  try {
    const data = await api.getAgent(body);
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

[**Agent**](Agent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Agent. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Agent not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAgentConversation

> AgentConversation getAgentConversation(id)

Fetch one agent conversation.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { GetAgentConversationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetAgentConversationRequest;

  try {
    const data = await api.getAgentConversation(body);
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

[**AgentConversation**](AgentConversation.md)

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
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAgentSessionContext

> AgentSessionContext getAgentSessionContext()

Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn\&#39;t fish on its first turn. 

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { GetAgentSessionContextRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  try {
    const data = await api.getAgentSessionContext();
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

[**AgentSessionContext**](AgentSessionContext.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Session context. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAgentConversationMessages

> AgentMessageListResponse listAgentConversationMessages(id)

List messages on an agent conversation.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { ListAgentConversationMessagesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies ListAgentConversationMessagesRequest;

  try {
    const data = await api.listAgentConversationMessages(body);
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

[**AgentMessageListResponse**](AgentMessageListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAgentConversations

> AgentConversationListResponse listAgentConversations()

List the caller\&#39;s agent-platform conversations. Distinct from &#x60;/v1/conversations&#x60; (renderer-driven sidebar persistence). 

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { ListAgentConversationsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  try {
    const data = await api.listAgentConversations();
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

[**AgentConversationListResponse**](AgentConversationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversation envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAgents

> AgentListResponse listAgents()

List the caller\&#39;s agent configurations.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { ListAgentsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  try {
    const data = await api.listAgents();
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

[**AgentListResponse**](AgentListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Agent list envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPreconfiguredAgents

> Array&lt;PreconfiguredAgent&gt; listPreconfiguredAgents()

Curated featured agents (e.g. \&quot;Claude Code\&quot;, \&quot;Research Assistant\&quot;). Read-only — these are surfaced by the renderer\&#39;s preconfigured-picker UI. 

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { ListPreconfiguredAgentsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  try {
    const data = await api.listPreconfiguredAgents();
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

[**Array&lt;PreconfiguredAgent&gt;**](PreconfiguredAgent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bare array of preconfigured agents. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAgent

> Agent updateAgent(id, updateAgentRequest)

Update an agent configuration.

### Example

```ts
import {
  Configuration,
  AgentsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateAgentOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AgentsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateAgentRequest
    updateAgentRequest: ...,
  } satisfies UpdateAgentOperationRequest;

  try {
    const data = await api.updateAgent(body);
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
| **updateAgentRequest** | [UpdateAgentRequest](UpdateAgentRequest.md) |  | |

### Return type

[**Agent**](Agent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated agent. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

