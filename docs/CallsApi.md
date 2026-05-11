# CallsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCall**](CallsApi.md#createcalloperation) | **POST** /v1/calls | Start a new call. |
| [**createMeetingRoom**](CallsApi.md#createmeetingroomoperation) | **POST** /v1/calls/rooms | Create a persistent meeting room. |
| [**deleteCallRecording**](CallsApi.md#deletecallrecording) | **DELETE** /v1/calls/recordings/{recordingId} | Delete a recording. |
| [**endCall**](CallsApi.md#endcall) | **POST** /v1/calls/{id}/end | End a call (host only). |
| [**getBandwidthHistory**](CallsApi.md#getbandwidthhistory) | **GET** /v1/calls/bandwidth/history | Time-series bandwidth metrics. |
| [**getBandwidthSummary**](CallsApi.md#getbandwidthsummary) | **GET** /v1/calls/bandwidth/summary | Aggregate bandwidth metrics. |
| [**getCall**](CallsApi.md#getcall) | **GET** /v1/calls/{id} | Fetch a call. |
| [**getMeetingRoom**](CallsApi.md#getmeetingroom) | **GET** /v1/calls/rooms/{id} | Fetch a meeting room. |
| [**joinCall**](CallsApi.md#joincall) | **POST** /v1/calls/{id}/join | Join a call. |
| [**leaveCall**](CallsApi.md#leavecall) | **POST** /v1/calls/{id}/leave | Leave a call. |
| [**listActiveCalls**](CallsApi.md#listactivecalls) | **GET** /v1/calls | List active calls. |
| [**listCallRecordings**](CallsApi.md#listcallrecordings) | **GET** /v1/calls/{id}/recordings | List recordings for a call. |
| [**startCallRecording**](CallsApi.md#startcallrecording) | **POST** /v1/calls/{id}/recordings/start | Start a recording (host only). |
| [**stopCallRecording**](CallsApi.md#stopcallrecording) | **POST** /v1/calls/{id}/recordings/{recordingId}/stop | Stop an in-progress recording. |
| [**updateCallParticipantState**](CallsApi.md#updatecallparticipantstate) | **PATCH** /v1/calls/{id}/participant | Toggle participant audio/video/screen-share state. |
| [**workspaceCreateCall**](CallsApi.md#workspacecreatecall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls |  |
| [**workspaceCreateMeetingRoom**](CallsApi.md#workspacecreatemeetingroom) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/rooms |  |
| [**workspaceDeleteCallRecording**](CallsApi.md#workspacedeletecallrecording) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/calls/recordings/{recordingId} |  |
| [**workspaceEndCall**](CallsApi.md#workspaceendcall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/end |  |
| [**workspaceGetBandwidthHistory**](CallsApi.md#workspacegetbandwidthhistory) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/bandwidth/history |  |
| [**workspaceGetBandwidthSummary**](CallsApi.md#workspacegetbandwidthsummary) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/bandwidth/summary |  |
| [**workspaceGetCall**](CallsApi.md#workspacegetcall) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/{id} |  |
| [**workspaceGetMeetingRoom**](CallsApi.md#workspacegetmeetingroom) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/rooms/{id} |  |
| [**workspaceJoinCall**](CallsApi.md#workspacejoincall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/join |  |
| [**workspaceLeaveCall**](CallsApi.md#workspaceleavecall) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/leave |  |
| [**workspaceListActiveCalls**](CallsApi.md#workspacelistactivecalls) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls |  |
| [**workspaceListCallRecordings**](CallsApi.md#workspacelistcallrecordings) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings |  |
| [**workspaceStartCallRecording**](CallsApi.md#workspacestartcallrecording) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings/start |  |
| [**workspaceStopCallRecording**](CallsApi.md#workspacestopcallrecording) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings/{recordingId}/stop |  |
| [**workspaceUpdateCallParticipant**](CallsApi.md#workspaceupdatecallparticipant) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/participant |  |



## createCall

> SpatioCall createCall(createCallRequest)

Start a new call.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateCallOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // CreateCallRequest (optional)
    createCallRequest: ...,
  } satisfies CreateCallOperationRequest;

  try {
    const data = await api.createCall(body);
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
| **createCallRequest** | [CreateCallRequest](CreateCallRequest.md) |  | [Optional] |

### Return type

[**SpatioCall**](SpatioCall.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created call. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createMeetingRoom

> MeetingRoom createMeetingRoom(createMeetingRoomRequest)

Create a persistent meeting room.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { CreateMeetingRoomOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // CreateMeetingRoomRequest
    createMeetingRoomRequest: ...,
  } satisfies CreateMeetingRoomOperationRequest;

  try {
    const data = await api.createMeetingRoom(body);
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
| **createMeetingRoomRequest** | [CreateMeetingRoomRequest](CreateMeetingRoomRequest.md) |  | |

### Return type

[**MeetingRoom**](MeetingRoom.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created room. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteCallRecording

> deleteCallRecording(recordingId)

Delete a recording.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteCallRecordingRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    recordingId: recordingId_example,
  } satisfies DeleteCallRecordingRequest;

  try {
    const data = await api.deleteCallRecording(body);
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
| **recordingId** | `string` |  | [Defaults to `undefined`] |

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


## endCall

> endCall(id)

End a call (host only).

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { EndCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies EndCallRequest;

  try {
    const data = await api.endCall(body);
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
| **204** | Ended. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getBandwidthHistory

> { [key: string]: any; } getBandwidthHistory()

Time-series bandwidth metrics.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { GetBandwidthHistoryRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  try {
    const data = await api.getBandwidthHistory();
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
| **200** | History (open shape). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getBandwidthSummary

> { [key: string]: any; } getBandwidthSummary()

Aggregate bandwidth metrics.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { GetBandwidthSummaryRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  try {
    const data = await api.getBandwidthSummary();
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
| **200** | Summary (open shape — provider-tied). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getCall

> SpatioCall getCall(id)

Fetch a call.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { GetCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetCallRequest;

  try {
    const data = await api.getCall(body);
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

[**SpatioCall**](SpatioCall.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Call. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMeetingRoom

> MeetingRoom getMeetingRoom(id)

Fetch a meeting room.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { GetMeetingRoomRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetMeetingRoomRequest;

  try {
    const data = await api.getMeetingRoom(body);
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

[**MeetingRoom**](MeetingRoom.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Meeting room. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## joinCall

> { [key: string]: any; } joinCall(id)

Join a call.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { JoinCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies JoinCallRequest;

  try {
    const data = await api.joinCall(body);
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

**{ [key: string]: any; }**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Join state envelope (provider-tied). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## leaveCall

> leaveCall(id)

Leave a call.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { LeaveCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies LeaveCallRequest;

  try {
    const data = await api.leaveCall(body);
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
| **204** | Left. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listActiveCalls

> CallListResponse listActiveCalls()

List active calls.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { ListActiveCallsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  try {
    const data = await api.listActiveCalls();
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

[**CallListResponse**](CallListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Call list envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCallRecordings

> CallRecordingListResponse listCallRecordings(id)

List recordings for a call.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { ListCallRecordingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies ListCallRecordingsRequest;

  try {
    const data = await api.listCallRecordings(body);
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

[**CallRecordingListResponse**](CallRecordingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recording envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## startCallRecording

> CallRecording startCallRecording(id)

Start a recording (host only).

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { StartCallRecordingRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies StartCallRecordingRequest;

  try {
    const data = await api.startCallRecording(body);
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

[**CallRecording**](CallRecording.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recording. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## stopCallRecording

> CallRecording stopCallRecording(id, recordingId)

Stop an in-progress recording.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { StopCallRecordingRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
    // string
    recordingId: recordingId_example,
  } satisfies StopCallRecordingRequest;

  try {
    const data = await api.stopCallRecording(body);
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
| **recordingId** | `string` |  | [Defaults to `undefined`] |

### Return type

[**CallRecording**](CallRecording.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recording. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateCallParticipantState

> { [key: string]: any; } updateCallParticipantState(id, updateParticipantStateRequest)

Toggle participant audio/video/screen-share state.

### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateCallParticipantStateRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateParticipantStateRequest
    updateParticipantStateRequest: ...,
  } satisfies UpdateCallParticipantStateRequest;

  try {
    const data = await api.updateCallParticipantState(body);
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
| **updateParticipantStateRequest** | [UpdateParticipantStateRequest](UpdateParticipantStateRequest.md) |  | |

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
| **200** | Updated state envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateCall

> { [key: string]: any; } workspaceCreateCall(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceCreateCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateCallRequest;

  try {
    const data = await api.workspaceCreateCall(body);
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


## workspaceCreateMeetingRoom

> { [key: string]: any; } workspaceCreateMeetingRoom(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceCreateMeetingRoomRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateMeetingRoomRequest;

  try {
    const data = await api.workspaceCreateMeetingRoom(body);
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


## workspaceDeleteCallRecording

> workspaceDeleteCallRecording(org, workspace, recordingId)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceDeleteCallRecordingRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    recordingId: recordingId_example,
  } satisfies WorkspaceDeleteCallRecordingRequest;

  try {
    const data = await api.workspaceDeleteCallRecording(body);
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
| **recordingId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceEndCall

> workspaceEndCall(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceEndCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceEndCallRequest;

  try {
    const data = await api.workspaceEndCall(body);
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

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Ended |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetBandwidthHistory

> { [key: string]: any; } workspaceGetBandwidthHistory(org, workspace)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetBandwidthHistoryRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceGetBandwidthHistoryRequest;

  try {
    const data = await api.workspaceGetBandwidthHistory(body);
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
| **200** | History |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetBandwidthSummary

> { [key: string]: any; } workspaceGetBandwidthSummary(org, workspace)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetBandwidthSummaryRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceGetBandwidthSummaryRequest;

  try {
    const data = await api.workspaceGetBandwidthSummary(body);
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
| **200** | Summary |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetCall

> { [key: string]: any; } workspaceGetCall(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetCallRequest;

  try {
    const data = await api.workspaceGetCall(body);
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
| **200** | Call |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetMeetingRoom

> { [key: string]: any; } workspaceGetMeetingRoom(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetMeetingRoomRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetMeetingRoomRequest;

  try {
    const data = await api.workspaceGetMeetingRoom(body);
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
| **200** | Room |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceJoinCall

> { [key: string]: any; } workspaceJoinCall(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceJoinCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceJoinCallRequest;

  try {
    const data = await api.workspaceJoinCall(body);
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
| **200** | Joined |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceLeaveCall

> workspaceLeaveCall(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceLeaveCallRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceLeaveCallRequest;

  try {
    const data = await api.workspaceLeaveCall(body);
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

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Left |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListActiveCalls

> { [key: string]: any; } workspaceListActiveCalls(org, workspace)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListActiveCallsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListActiveCallsRequest;

  try {
    const data = await api.workspaceListActiveCalls(body);
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
| **200** | Calls |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListCallRecordings

> { [key: string]: any; } workspaceListCallRecordings(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListCallRecordingsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceListCallRecordingsRequest;

  try {
    const data = await api.workspaceListCallRecordings(body);
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
| **200** | Recordings |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceStartCallRecording

> { [key: string]: any; } workspaceStartCallRecording(org, workspace, id)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceStartCallRecordingRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceStartCallRecordingRequest;

  try {
    const data = await api.workspaceStartCallRecording(body);
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
| **200** | Started |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceStopCallRecording

> { [key: string]: any; } workspaceStopCallRecording(org, workspace, id, recordingId)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceStopCallRecordingRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // string
    recordingId: recordingId_example,
  } satisfies WorkspaceStopCallRecordingRequest;

  try {
    const data = await api.workspaceStopCallRecording(body);
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
| **recordingId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Stopped |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceUpdateCallParticipant

> { [key: string]: any; } workspaceUpdateCallParticipant(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  CallsApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceUpdateCallParticipantRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CallsApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateCallParticipantRequest;

  try {
    const data = await api.workspaceUpdateCallParticipant(body);
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
| **200** | Updated |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

