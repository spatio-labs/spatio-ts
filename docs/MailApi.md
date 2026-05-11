# MailApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**bulkArchiveEmails**](MailApi.md#bulkarchiveemails) | **POST** /v1/mail/archive | Archive multiple messages (remove the INBOX label). |
| [**bulkDeleteEmails**](MailApi.md#bulkdeleteemailsoperation) | **POST** /v1/mail/delete | Delete multiple messages in one call. |
| [**bulkMarkEmailsRead**](MailApi.md#bulkmarkemailsread) | **POST** /v1/mail/mark-read | Mark multiple messages read or unread in one call. |
| [**createDraft**](MailApi.md#createdraftoperation) | **POST** /v1/mail/drafts | Create a draft. |
| [**createEmailLabel**](MailApi.md#createemaillabel) | **POST** /v1/mail/labels | Create a label. |
| [**createMailTemplate**](MailApi.md#createmailtemplate) | **POST** /v1/mail/templates | Create a mail template. |
| [**deleteDraft**](MailApi.md#deletedraft) | **DELETE** /v1/mail/drafts/{id} | Delete a draft. |
| [**deleteEmail**](MailApi.md#deleteemail) | **DELETE** /v1/mail/email/{id} | Delete an email. |
| [**deleteEmailLabel**](MailApi.md#deleteemaillabel) | **DELETE** /v1/mail/labels/{id} | Delete a label. |
| [**deleteMailTemplate**](MailApi.md#deletemailtemplate) | **DELETE** /v1/mail/templates/{id} | Delete a mail template. |
| [**getEmail**](MailApi.md#getemail) | **GET** /v1/mail/email/{id} | Fetch one email. |
| [**getEmailAttachment**](MailApi.md#getemailattachment) | **GET** /v1/mail/attachment/{messageId}/{attachmentId} | Download an attachment. |
| [**getEmailThread**](MailApi.md#getemailthread) | **GET** /v1/mail/thread/{id} | Fetch a thread (the conversation a message belongs to). |
| [**getMailTemplate**](MailApi.md#getmailtemplate) | **GET** /v1/mail/templates/{id} | Fetch a mail template. |
| [**getMailThreadTracking**](MailApi.md#getmailthreadtracking) | **GET** /v1/mail/threads/{threadId}/tracking | Read mail-tracking events for a thread (open log, reply log, etc.). |
| [**instantiateMailTemplate**](MailApi.md#instantiatemailtemplate) | **POST** /v1/mail/templates/{id}/instantiate | Render a template with variables and return the resulting draft. |
| [**listDrafts**](MailApi.md#listdrafts) | **GET** /v1/mail/drafts | List drafts across connected mail accounts. |
| [**listEmailLabels**](MailApi.md#listemaillabels) | **GET** /v1/mail/labels | List labels on the resolved mail account. |
| [**listEmails**](MailApi.md#listemails) | **GET** /v1/mail/list | List emails across connected mail accounts. |
| [**listMailTemplates**](MailApi.md#listmailtemplates) | **GET** /v1/mail/templates | List the caller\&#39;s saved mail templates. |
| [**replyEmail**](MailApi.md#replyemailoperation) | **POST** /v1/mail/reply | Reply to a specific email. |
| [**saveMailTemplate**](MailApi.md#savemailtemplate) | **POST** /v1/mail/templates/save | Save-or-create endpoint used by the renderer\&#39;s \&quot;save as template\&quot; flow. Distinct from POST /v1/mail/templates which is the strict create.  |
| [**searchEmails**](MailApi.md#searchemails) | **GET** /v1/mail/search | Structured search across connected mail accounts. |
| [**sendDraft**](MailApi.md#senddraft) | **POST** /v1/mail/drafts/{id}/send | Send a draft. |
| [**sendEmail**](MailApi.md#sendemailoperation) | **POST** /v1/mail/send | Send an email. |
| [**updateDraft**](MailApi.md#updatedraftoperation) | **PUT** /v1/mail/drafts/{id} | Update a draft (full replacement of provided fields). |
| [**updateEmail**](MailApi.md#updateemailoperation) | **PATCH** /v1/mail/email/{id} | Update an email (mark read/star, add/remove labels). |
| [**updateMailTemplate**](MailApi.md#updatemailtemplate) | **PATCH** /v1/mail/templates/{id} | Update a mail template. |
| [**workspaceAddMailMessageLabels**](MailApi.md#workspaceaddmailmessagelabels) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/{messageId}/labels |  |
| [**workspaceCreateMailDraft**](MailApi.md#workspacecreatemaildraft) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts |  |
| [**workspaceCreateMailLabel**](MailApi.md#workspacecreatemaillabel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/labels |  |
| [**workspaceDeleteMail**](MailApi.md#workspacedeletemail) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspaceDeleteMailDraft**](MailApi.md#workspacedeletemaildraft) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id} |  |
| [**workspaceDeleteMailLabel**](MailApi.md#workspacedeletemaillabel) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/labels/{id} |  |
| [**workspaceGetMail**](MailApi.md#workspacegetmail) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspaceGetMailAttachment**](MailApi.md#workspacegetmailattachment) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/attachment/{messageId}/{attachmentId} |  |
| [**workspaceGetMailById**](MailApi.md#workspacegetmailbyid) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/{id} | Workspace-scoped renderer-compat alias for mail/email/{id}. |
| [**workspaceGetMailDraft**](MailApi.md#workspacegetmaildraft) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id} |  |
| [**workspaceGetMailThread**](MailApi.md#workspacegetmailthread) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/thread/{id} |  |
| [**workspaceListMail**](MailApi.md#workspacelistmail) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/list |  |
| [**workspaceListMailDrafts**](MailApi.md#workspacelistmaildrafts) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts |  |
| [**workspaceListMailLabels**](MailApi.md#workspacelistmaillabels) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/labels |  |
| [**workspacePatchMail**](MailApi.md#workspacepatchmail) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspaceRemoveMailMessageLabel**](MailApi.md#workspaceremovemailmessagelabel) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/{messageId}/labels/{labelId} |  |
| [**workspaceReplyMail**](MailApi.md#workspacereplymail) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/reply |  |
| [**workspaceSearchMail**](MailApi.md#workspacesearchmail) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/search |  |
| [**workspaceSendMail**](MailApi.md#workspacesendmail) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/send |  |
| [**workspaceSendMailDraft**](MailApi.md#workspacesendmaildraft) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id}/send |  |
| [**workspaceSendMailEmailAlias**](MailApi.md#workspacesendmailemailalias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/email | Renderer-compat alias for /mail/send. |
| [**workspaceUpdateMail**](MailApi.md#workspaceupdatemail) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspaceUpdateMailDraft**](MailApi.md#workspaceupdatemaildraft) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id} |  |
| [**workspaceUpdateMailLabel**](MailApi.md#workspaceupdatemaillabel) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/mail/labels/{id} |  |



## bulkArchiveEmails

> BulkArchiveResponse bulkArchiveEmails(bulkArchiveRequest)

Archive multiple messages (remove the INBOX label).

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { BulkArchiveEmailsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // BulkArchiveRequest
    bulkArchiveRequest: ...,
  } satisfies BulkArchiveEmailsRequest;

  try {
    const data = await api.bulkArchiveEmails(body);
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
| **bulkArchiveRequest** | [BulkArchiveRequest](BulkArchiveRequest.md) |  | |

### Return type

[**BulkArchiveResponse**](BulkArchiveResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Partial-success envelope. |  -  |
| **400** | Body missing or empty. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## bulkDeleteEmails

> BulkDeleteEmailsResponse bulkDeleteEmails(bulkDeleteEmailsRequest)

Delete multiple messages in one call.

Soft-delete by default (moves to provider trash). Set &#x60;permanent: true&#x60; for a hard delete. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { BulkDeleteEmailsOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // BulkDeleteEmailsRequest
    bulkDeleteEmailsRequest: ...,
  } satisfies BulkDeleteEmailsOperationRequest;

  try {
    const data = await api.bulkDeleteEmails(body);
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
| **bulkDeleteEmailsRequest** | [BulkDeleteEmailsRequest](BulkDeleteEmailsRequest.md) |  | |

### Return type

[**BulkDeleteEmailsResponse**](BulkDeleteEmailsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Partial-success envelope. |  -  |
| **400** | Body missing or empty. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## bulkMarkEmailsRead

> BulkMarkReadResponse bulkMarkEmailsRead(bulkMarkReadRequest)

Mark multiple messages read or unread in one call.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { BulkMarkEmailsReadRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // BulkMarkReadRequest
    bulkMarkReadRequest: ...,
  } satisfies BulkMarkEmailsReadRequest;

  try {
    const data = await api.bulkMarkEmailsRead(body);
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
| **bulkMarkReadRequest** | [BulkMarkReadRequest](BulkMarkReadRequest.md) |  | |

### Return type

[**BulkMarkReadResponse**](BulkMarkReadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Partial-success envelope. |  -  |
| **400** | Body missing or empty. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createDraft

> DraftResponse createDraft(createDraftRequest, xWorkspaceID)

Create a draft.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { CreateDraftOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // CreateDraftRequest
    createDraftRequest: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateDraftOperationRequest;

  try {
    const data = await api.createDraft(body);
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
| **createDraftRequest** | [CreateDraftRequest](CreateDraftRequest.md) |  | |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**DraftResponse**](DraftResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Draft created. |  -  |
| **400** | Invalid body or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createEmailLabel

> CreateLabelResponse createEmailLabel(createLabelRequest, accountId, xWorkspaceID)

Create a label.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { CreateEmailLabelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // CreateLabelRequest
    createLabelRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies CreateEmailLabelRequest;

  try {
    const data = await api.createEmailLabel(body);
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
| **createLabelRequest** | [CreateLabelRequest](CreateLabelRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**CreateLabelResponse**](CreateLabelResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Label created. |  -  |
| **400** | Invalid body or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createMailTemplate

> { [key: string]: any; } createMailTemplate(requestBody)

Create a mail template.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { CreateMailTemplateRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateMailTemplateRequest;

  try {
    const data = await api.createMailTemplate(body);
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
| **201** | Created template. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteDraft

> deleteDraft(id, accountId, xWorkspaceID)

Delete a draft.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Draft id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteDraftRequest;

  try {
    const data = await api.deleteDraft(body);
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
| **id** | `string` | Draft id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

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
| **204** | Draft deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Draft not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteEmail

> SuccessFlag deleteEmail(id, accountId, xWorkspaceID)

Delete an email.

Soft-deletes (moves to provider trash).

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteEmailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Email message id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteEmailRequest;

  try {
    const data = await api.deleteEmail(body);
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
| **id** | `string` | Email message id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

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
| **404** | Message not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteEmailLabel

> deleteEmailLabel(id, accountId, xWorkspaceID)

Delete a label.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteEmailLabelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Label id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies DeleteEmailLabelRequest;

  try {
    const data = await api.deleteEmailLabel(body);
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
| **id** | `string` | Label id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

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
| **204** | Label deleted. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Label not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteMailTemplate

> deleteMailTemplate(id)

Delete a mail template.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { DeleteMailTemplateRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies DeleteMailTemplateRequest;

  try {
    const data = await api.deleteMailTemplate(body);
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


## getEmail

> GetEmailResponse getEmail(id, accountId, xWorkspaceID)

Fetch one email.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { GetEmailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Email message id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetEmailRequest;

  try {
    const data = await api.getEmail(body);
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
| **id** | `string` | Email message id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**GetEmailResponse**](GetEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The email. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Message not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEmailAttachment

> Blob getEmailAttachment(messageId, attachmentId, accountId, xWorkspaceID)

Download an attachment.

Streams the attachment binary. Response &#x60;Content-Type&#x60; matches the attachment\&#39;s declared MIME type; &#x60;Content-Disposition&#x60; sets the filename. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { GetEmailAttachmentRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Message id the attachment belongs to.
    messageId: messageId_example,
    // string | Attachment id within the message.
    attachmentId: attachmentId_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetEmailAttachmentRequest;

  try {
    const data = await api.getEmailAttachment(body);
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
| **messageId** | `string` | Message id the attachment belongs to. | [Defaults to `undefined`] |
| **attachmentId** | `string` | Attachment id within the message. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

**Blob**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`, `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The attachment binary. |  -  |
| **400** | Missing ids or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Attachment not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEmailThread

> GetThreadResponse getEmailThread(id, accountId, xWorkspaceID)

Fetch a thread (the conversation a message belongs to).

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { GetEmailThreadRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Thread id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies GetEmailThreadRequest;

  try {
    const data = await api.getEmailThread(body);
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
| **id** | `string` | Thread id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**GetThreadResponse**](GetThreadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The thread. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Thread not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMailTemplate

> { [key: string]: any; } getMailTemplate(id)

Fetch a mail template.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { GetMailTemplateRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    id: id_example,
  } satisfies GetMailTemplateRequest;

  try {
    const data = await api.getMailTemplate(body);
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
| **200** | Template. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMailThreadTracking

> { [key: string]: any; } getMailThreadTracking(threadId)

Read mail-tracking events for a thread (open log, reply log, etc.).

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { GetMailThreadTrackingRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    threadId: threadId_example,
  } satisfies GetMailThreadTrackingRequest;

  try {
    const data = await api.getMailThreadTracking(body);
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
| **threadId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Tracking events. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## instantiateMailTemplate

> { [key: string]: any; } instantiateMailTemplate(id, requestBody)

Render a template with variables and return the resulting draft.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { InstantiateMailTemplateRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies InstantiateMailTemplateRequest;

  try {
    const data = await api.instantiateMailTemplate(body);
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
| **200** | Rendered draft. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDrafts

> ListDraftsResponse listDrafts(xWorkspaceID, accountIds, providers, limit, nextPageToken)

List drafts across connected mail accounts.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { ListDraftsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // Array<string> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.  (optional)
    accountIds: ...,
    // Array<string> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`). (optional)
    providers: ...,
    // number (optional)
    limit: 56,
    // string (optional)
    nextPageToken: nextPageToken_example,
  } satisfies ListDraftsRequest;

  try {
    const data = await api.listDrafts(body);
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
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **accountIds** | `Array<string>` | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [Optional] |
| **providers** | `Array<string>` | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [Optional] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **nextPageToken** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**ListDraftsResponse**](ListDraftsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Draft list. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listEmailLabels

> ListLabelsResponse listEmailLabels(accountId, xWorkspaceID)

List labels on the resolved mail account.

Single-account list. The platform auto-resolves to the caller\&#39;s sole connected account; pass &#x60;?accountId&#x3D;&#x60; to disambiguate when multiple are connected. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { ListEmailLabelsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies ListEmailLabelsRequest;

  try {
    const data = await api.listEmailLabels(body);
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
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**ListLabelsResponse**](ListLabelsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Label list. |  -  |
| **400** | Ambiguous account or no mail provider connected. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listEmails

> ListEmailsResponse listEmails(accountIds, providers, xWorkspaceID, query, labels, folder, limit, offset)

List emails across connected mail accounts.

Fan-out list. Returns messages across every connected mail provider unless filtered. Pass &#x60;?accountIds&#x3D;&#x60; (repeatable) to restrict to specific accounts, &#x60;?providers&#x3D;&#x60; to restrict to specific provider ids, or both for the intersection. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { ListEmailsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // Array<string> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.  (optional)
    accountIds: ...,
    // Array<string> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`). (optional)
    providers: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // string | Provider-specific full-text query (e.g. Gmail search syntax). (optional)
    query: query_example,
    // Array<string> | Repeatable. Filter to messages carrying every label. (optional)
    labels: ...,
    // string | Logical folder filter. Canonical values: `inbox`, `sent`, `starred`, `trash`, `archive`. Provider-specific folders accepted as opaque strings.  (optional)
    folder: folder_example,
    // number (optional)
    limit: 56,
    // number (optional)
    offset: 56,
  } satisfies ListEmailsRequest;

  try {
    const data = await api.listEmails(body);
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
| **query** | `string` | Provider-specific full-text query (e.g. Gmail search syntax). | [Optional] [Defaults to `undefined`] |
| **labels** | `Array<string>` | Repeatable. Filter to messages carrying every label. | [Optional] |
| **folder** | `string` | Logical folder filter. Canonical values: &#x60;inbox&#x60;, &#x60;sent&#x60;, &#x60;starred&#x60;, &#x60;trash&#x60;, &#x60;archive&#x60;. Provider-specific folders accepted as opaque strings.  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **offset** | `number` |  | [Optional] [Defaults to `0`] |

### Return type

[**ListEmailsResponse**](ListEmailsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Email list. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Resolver or fan-out failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listMailTemplates

> { [key: string]: any; } listMailTemplates()

List the caller\&#39;s saved mail templates.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { ListMailTemplatesRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  try {
    const data = await api.listMailTemplates();
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
| **200** | Template envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## replyEmail

> SendEmailResponse replyEmail(messageId, replyEmailRequest, xWorkspaceID)

Reply to a specific email.

The original message is identified by &#x60;?messageId&#x3D;&#x60;. Body defaults to the original sender as recipient — pass &#x60;to&#x60;, &#x60;cc&#x60;, &#x60;bcc&#x60; to override. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { ReplyEmailOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Id of the message being replied to.
    messageId: messageId_example,
    // ReplyEmailRequest
    replyEmailRequest: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies ReplyEmailOperationRequest;

  try {
    const data = await api.replyEmail(body);
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
| **messageId** | `string` | Id of the message being replied to. | [Defaults to `undefined`] |
| **replyEmailRequest** | [ReplyEmailRequest](ReplyEmailRequest.md) |  | |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SendEmailResponse**](SendEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Send result. |  -  |
| **400** | Missing messageId or invalid body. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Original message not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## saveMailTemplate

> { [key: string]: any; } saveMailTemplate(requestBody)

Save-or-create endpoint used by the renderer\&#39;s \&quot;save as template\&quot; flow. Distinct from POST /v1/mail/templates which is the strict create. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { SaveMailTemplateRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies SaveMailTemplateRequest;

  try {
    const data = await api.saveMailTemplate(body);
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
| **200** | Saved template. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchEmails

> SearchEmailsResponse searchEmails(q, accountIds, providers, xWorkspaceID, from, to, subject, hasAttachment, isUnread, isStarred, labels, after, before, limit, nextPageToken)

Structured search across connected mail accounts.

Fan-out search. Mirrors &#x60;listEmails&#x60;\&#39;s account/provider filter semantics. Date range filters are inclusive. The query string itself is passed via &#x60;?q&#x3D;&#x60; (not &#x60;?query&#x3D;&#x60;); structured filters go in their own params. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { SearchEmailsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Provider-specific full-text query string.
    q: q_example,
    // Array<string> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used.  (optional)
    accountIds: ...,
    // Array<string> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`). (optional)
    providers: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
    // string (optional)
    from: from_example,
    // string (optional)
    to: to_example,
    // string (optional)
    subject: subject_example,
    // boolean (optional)
    hasAttachment: true,
    // boolean (optional)
    isUnread: true,
    // boolean (optional)
    isStarred: true,
    // Array<string> (optional)
    labels: ...,
    // Date | Inclusive lower-bound date. (optional)
    after: 2013-10-20T19:20:30+01:00,
    // Date | Inclusive upper-bound date. (optional)
    before: 2013-10-20T19:20:30+01:00,
    // number (optional)
    limit: 56,
    // string | Cursor returned by the previous call. (optional)
    nextPageToken: nextPageToken_example,
  } satisfies SearchEmailsRequest;

  try {
    const data = await api.searchEmails(body);
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
| **q** | `string` | Provider-specific full-text query string. | [Defaults to `undefined`] |
| **accountIds** | `Array<string>` | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [Optional] |
| **providers** | `Array<string>` | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [Optional] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |
| **from** | `string` |  | [Optional] [Defaults to `undefined`] |
| **to** | `string` |  | [Optional] [Defaults to `undefined`] |
| **subject** | `string` |  | [Optional] [Defaults to `undefined`] |
| **hasAttachment** | `boolean` |  | [Optional] [Defaults to `undefined`] |
| **isUnread** | `boolean` |  | [Optional] [Defaults to `undefined`] |
| **isStarred** | `boolean` |  | [Optional] [Defaults to `undefined`] |
| **labels** | `Array<string>` |  | [Optional] |
| **after** | `Date` | Inclusive lower-bound date. | [Optional] [Defaults to `undefined`] |
| **before** | `Date` | Inclusive upper-bound date. | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `50`] |
| **nextPageToken** | `string` | Cursor returned by the previous call. | [Optional] [Defaults to `undefined`] |

### Return type

[**SearchEmailsResponse**](SearchEmailsResponse.md)

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
| **500** | Resolver or provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## sendDraft

> SendEmailResponse sendDraft(id, accountId, xWorkspaceID)

Send a draft.

Submits the draft as an outbound message. The draft is consumed by the provider — subsequent &#x60;getDraft&#x60;/&#x60;updateDraft&#x60; calls return &#x60;404&#x60;. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { SendDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Draft id.
    id: id_example,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies SendDraftRequest;

  try {
    const data = await api.sendDraft(body);
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
| **id** | `string` | Draft id. | [Defaults to `undefined`] |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SendEmailResponse**](SendEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Send result. |  -  |
| **400** | Missing id or ambiguous account. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Draft not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## sendEmail

> SendEmailResponse sendEmail(sendEmailRequest, xWorkspaceID)

Send an email.

Sends through the resolved connected account (auto-picks if the caller has exactly one connected mail account; errors &#x60;ambiguous_account&#x60; otherwise unless &#x60;accountId&#x60; is supplied). 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { SendEmailOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // SendEmailRequest
    sendEmailRequest: ...,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies SendEmailOperationRequest;

  try {
    const data = await api.sendEmail(body);
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
| **sendEmailRequest** | [SendEmailRequest](SendEmailRequest.md) |  | |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**SendEmailResponse**](SendEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Send result. |  -  |
| **400** | Invalid body, ambiguous account (&#x60;code: ambiguous_account&#x60;), or no mail provider connected (&#x60;code: no_mail_provider&#x60;).  |  -  |
| **401** | Caller is not authenticated. |  -  |
| **500** | Provider failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateDraft

> DraftResponse updateDraft(id, updateDraftRequest, accountId, xWorkspaceID)

Update a draft (full replacement of provided fields).

PUT replaces the full set of provided fields on the draft. Fields omitted from the body are not modified. 

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateDraftOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Draft id.
    id: id_example,
    // UpdateDraftRequest
    updateDraftRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateDraftOperationRequest;

  try {
    const data = await api.updateDraft(body);
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
| **id** | `string` | Draft id. | [Defaults to `undefined`] |
| **updateDraftRequest** | [UpdateDraftRequest](UpdateDraftRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**DraftResponse**](DraftResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated draft. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Draft not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateEmail

> UpdateEmailResponse updateEmail(id, updateEmailRequest, accountId, xWorkspaceID)

Update an email (mark read/star, add/remove labels).

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateEmailOperationRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string | Email message id.
    id: id_example,
    // UpdateEmailRequest
    updateEmailRequest: ...,
    // string | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account.  (optional)
    accountId: accountId_example,
    // string | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  (optional)
    xWorkspaceID: xWorkspaceID_example,
  } satisfies UpdateEmailOperationRequest;

  try {
    const data = await api.updateEmail(body);
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
| **id** | `string` | Email message id. | [Defaults to `undefined`] |
| **updateEmailRequest** | [UpdateEmailRequest](UpdateEmailRequest.md) |  | |
| **accountId** | `string` | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [Optional] [Defaults to `undefined`] |
| **xWorkspaceID** | `string` | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [Optional] [Defaults to `undefined`] |

### Return type

[**UpdateEmailResponse**](UpdateEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated email. |  -  |
| **400** | Invalid body or missing id. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Message not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateMailTemplate

> { [key: string]: any; } updateMailTemplate(id, requestBody)

Update a mail template.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { UpdateMailTemplateRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies UpdateMailTemplateRequest;

  try {
    const data = await api.updateMailTemplate(body);
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


## workspaceAddMailMessageLabels

> { [key: string]: any; } workspaceAddMailMessageLabels(org, workspace, messageId, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceAddMailMessageLabelsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    messageId: messageId_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceAddMailMessageLabelsRequest;

  try {
    const data = await api.workspaceAddMailMessageLabels(body);
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
| **200** | Added |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateMailDraft

> { [key: string]: any; } workspaceCreateMailDraft(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceCreateMailDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateMailDraftRequest;

  try {
    const data = await api.workspaceCreateMailDraft(body);
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


## workspaceCreateMailLabel

> { [key: string]: any; } workspaceCreateMailLabel(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceCreateMailLabelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateMailLabelRequest;

  try {
    const data = await api.workspaceCreateMailLabel(body);
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


## workspaceDeleteMail

> workspaceDeleteMail(org, workspace, id)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceDeleteMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceDeleteMailRequest;

  try {
    const data = await api.workspaceDeleteMail(body);
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
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceDeleteMailDraft

> workspaceDeleteMailDraft(org, workspace, id)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceDeleteMailDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceDeleteMailDraftRequest;

  try {
    const data = await api.workspaceDeleteMailDraft(body);
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
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceDeleteMailLabel

> workspaceDeleteMailLabel(org, workspace, id)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceDeleteMailLabelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceDeleteMailLabelRequest;

  try {
    const data = await api.workspaceDeleteMailLabel(body);
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
| **204** | Deleted |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetMail

> { [key: string]: any; } workspaceGetMail(org, workspace, id)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetMailRequest;

  try {
    const data = await api.workspaceGetMail(body);
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
| **200** | Email |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetMailAttachment

> { [key: string]: any; } workspaceGetMailAttachment(org, workspace, messageId, attachmentId)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetMailAttachmentRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    messageId: messageId_example,
    // string
    attachmentId: attachmentId_example,
  } satisfies WorkspaceGetMailAttachmentRequest;

  try {
    const data = await api.workspaceGetMailAttachment(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |
| **attachmentId** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Attachment |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetMailById

> { [key: string]: any; } workspaceGetMailById(org, workspace, id)

Workspace-scoped renderer-compat alias for mail/email/{id}.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetMailByIdRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetMailByIdRequest;

  try {
    const data = await api.workspaceGetMailById(body);
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
| **200** | Email |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetMailDraft

> { [key: string]: any; } workspaceGetMailDraft(org, workspace, id)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetMailDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetMailDraftRequest;

  try {
    const data = await api.workspaceGetMailDraft(body);
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
| **200** | Draft |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetMailThread

> { [key: string]: any; } workspaceGetMailThread(org, workspace, id)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceGetMailThreadRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceGetMailThreadRequest;

  try {
    const data = await api.workspaceGetMailThread(body);
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
| **200** | Thread |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListMail

> { [key: string]: any; } workspaceListMail(org, workspace)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListMailRequest;

  try {
    const data = await api.workspaceListMail(body);
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
| **200** | Email list |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListMailDrafts

> { [key: string]: any; } workspaceListMailDrafts(org, workspace)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListMailDraftsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListMailDraftsRequest;

  try {
    const data = await api.workspaceListMailDrafts(body);
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
| **200** | Drafts |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListMailLabels

> { [key: string]: any; } workspaceListMailLabels(org, workspace)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceListMailLabelsRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListMailLabelsRequest;

  try {
    const data = await api.workspaceListMailLabels(body);
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
| **200** | Labels |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspacePatchMail

> { [key: string]: any; } workspacePatchMail(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspacePatchMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspacePatchMailRequest;

  try {
    const data = await api.workspacePatchMail(body);
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


## workspaceRemoveMailMessageLabel

> workspaceRemoveMailMessageLabel(org, workspace, messageId, labelId)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceRemoveMailMessageLabelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    messageId: messageId_example,
    // string
    labelId: labelId_example,
  } satisfies WorkspaceRemoveMailMessageLabelRequest;

  try {
    const data = await api.workspaceRemoveMailMessageLabel(body);
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
| **messageId** | `string` |  | [Defaults to `undefined`] |
| **labelId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | Removed |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceReplyMail

> { [key: string]: any; } workspaceReplyMail(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceReplyMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceReplyMailRequest;

  try {
    const data = await api.workspaceReplyMail(body);
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
| **200** | Replied |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceSearchMail

> { [key: string]: any; } workspaceSearchMail(org, workspace, q)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceSearchMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string (optional)
    q: q_example,
  } satisfies WorkspaceSearchMailRequest;

  try {
    const data = await api.workspaceSearchMail(body);
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
| **200** | Results |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceSendMail

> { [key: string]: any; } workspaceSendMail(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceSendMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceSendMailRequest;

  try {
    const data = await api.workspaceSendMail(body);
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


## workspaceSendMailDraft

> { [key: string]: any; } workspaceSendMailDraft(org, workspace, id)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceSendMailDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
  } satisfies WorkspaceSendMailDraftRequest;

  try {
    const data = await api.workspaceSendMailDraft(body);
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
| **200** | Sent |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceSendMailEmailAlias

> { [key: string]: any; } workspaceSendMailEmailAlias(org, workspace, requestBody)

Renderer-compat alias for /mail/send.

### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceSendMailEmailAliasRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceSendMailEmailAliasRequest;

  try {
    const data = await api.workspaceSendMailEmailAlias(body);
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


## workspaceUpdateMail

> { [key: string]: any; } workspaceUpdateMail(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceUpdateMailRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateMailRequest;

  try {
    const data = await api.workspaceUpdateMail(body);
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


## workspaceUpdateMailDraft

> { [key: string]: any; } workspaceUpdateMailDraft(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceUpdateMailDraftRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateMailDraftRequest;

  try {
    const data = await api.workspaceUpdateMailDraft(body);
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


## workspaceUpdateMailLabel

> { [key: string]: any; } workspaceUpdateMailLabel(org, workspace, id, requestBody)



### Example

```ts
import {
  Configuration,
  MailApi,
} from '@spatio-labs/spatio-ts';
import type { WorkspaceUpdateMailLabelRequest } from '@spatio-labs/spatio-ts';

async function example() {
  console.log("🚀 Testing @spatio-labs/spatio-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MailApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    id: id_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceUpdateMailLabelRequest;

  try {
    const data = await api.workspaceUpdateMailLabel(body);
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

