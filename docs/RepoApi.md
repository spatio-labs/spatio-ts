# RepoApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createRepoBranch**](RepoApi.md#createrepobranch) | **POST** /v1/repos/repositories/{owner}/{repo}/branches | Create a branch (from a base sha). |
| [**createRepoPullRequest**](RepoApi.md#createrepopullrequest) | **POST** /v1/repos/repositories/{owner}/{repo}/pulls | Open a pull request. |
| [**createRepoRepository**](RepoApi.md#createreporepository) | **POST** /v1/repos/repositories | Create a repository. |
| [**getRepoCommit**](RepoApi.md#getrepocommit) | **GET** /v1/repos/repositories/{owner}/{repo}/commits/{sha} | Fetch a single commit. |
| [**getRepoRepository**](RepoApi.md#getreporepository) | **GET** /v1/repos/repositories/{owner}/{repo} | Fetch a single repository. |
| [**linkRepoTask**](RepoApi.md#linkrepotaskoperation) | **POST** /v1/repos/repositories/{owner}/{repo}/tasks/link | Link an existing Spatio task to this repo, allocating a per-repo number. |
| [**listRepoBranches**](RepoApi.md#listrepobranches) | **GET** /v1/repos/repositories/{owner}/{repo}/branches | List branches on a repository. |
| [**listRepoCommits**](RepoApi.md#listrepocommits) | **GET** /v1/repos/repositories/{owner}/{repo}/commits | List commits on a repository. |
| [**listRepoPullRequests**](RepoApi.md#listrepopullrequests) | **GET** /v1/repos/repositories/{owner}/{repo}/pulls | List pull requests on a repository. |
| [**listRepoRepositories**](RepoApi.md#listreporepositories) | **GET** /v1/repos/repositories | List the caller\&#39;s accessible repositories. |
| [**listRepoTasks**](RepoApi.md#listrepotasks) | **GET** /v1/repos/repositories/{owner}/{repo}/tasks | List tasks linked to this repo (the \&quot;issues\&quot; surface). |
| [**listRepoWorkflows**](RepoApi.md#listrepoworkflows) | **GET** /v1/repos/repositories/{owner}/{repo}/workflows | List CI workflows. |
| [**mergeRepoPullRequest**](RepoApi.md#mergerepopullrequest) | **POST** /v1/repos/repositories/{owner}/{repo}/pulls/{number}/merge | Merge a pull request. |
| [**triggerRepoWorkflow**](RepoApi.md#triggerrepoworkflow) | **POST** /v1/repos/repositories/{owner}/{repo}/workflows/{id}/trigger | Trigger a workflow_dispatch run. |
| [**workspaceCreateRepoBranch**](RepoApi.md#workspacecreaterepobranch) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/branches |  |
| [**workspaceCreateRepoPullRequest**](RepoApi.md#workspacecreaterepopullrequest) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls |  |
| [**workspaceCreateRepoRepository**](RepoApi.md#workspacecreatereporepository) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories |  |
| [**workspaceGetRepoCommit**](RepoApi.md#workspacegetrepocommit) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/commits/{sha} |  |
| [**workspaceGetRepoRepository**](RepoApi.md#workspacegetreporepository) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo} |  |
| [**workspaceLinkRepoTask**](RepoApi.md#workspacelinkrepotask) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/tasks/link |  |
| [**workspaceListRepoBranches**](RepoApi.md#workspacelistrepobranches) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/branches |  |
| [**workspaceListRepoCommits**](RepoApi.md#workspacelistrepocommits) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/commits |  |
| [**workspaceListRepoPullRequests**](RepoApi.md#workspacelistrepopullrequests) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls |  |
| [**workspaceListRepoRepositories**](RepoApi.md#workspacelistreporepositories) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories |  |
| [**workspaceListRepoTasks**](RepoApi.md#workspacelistrepotasks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/tasks |  |
| [**workspaceListRepoWorkflows**](RepoApi.md#workspacelistrepoworkflows) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/workflows |  |
| [**workspaceMergeRepoPullRequest**](RepoApi.md#workspacemergerepopullrequest) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls/{number}/merge |  |
| [**workspaceTriggerRepoWorkflow**](RepoApi.md#workspacetriggerrepoworkflow) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/workflows/{id}/trigger |  |



## createRepoBranch

> { [key: string]: any; } createRepoBranch(owner, repo, requestBody)

Create a branch (from a base sha).

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { CreateRepoBranchRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateRepoBranchRequest;

  try {
    const data = await api.createRepoBranch(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
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
| **201** | Created branch. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createRepoPullRequest

> { [key: string]: any; } createRepoPullRequest(owner, repo, requestBody)

Open a pull request.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { CreateRepoPullRequestRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateRepoPullRequestRequest;

  try {
    const data = await api.createRepoPullRequest(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
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
| **201** | Created PR. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createRepoRepository

> { [key: string]: any; } createRepoRepository(requestBody)

Create a repository.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { CreateRepoRepositoryRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies CreateRepoRepositoryRequest;

  try {
    const data = await api.createRepoRepository(body);
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
| **201** | Created repo (provider-tied shape). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getRepoCommit

> { [key: string]: any; } getRepoCommit(owner, repo, sha)

Fetch a single commit.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { GetRepoCommitRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // string
    sha: sha_example,
  } satisfies GetRepoCommitRequest;

  try {
    const data = await api.getRepoCommit(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **sha** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Commit. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getRepoRepository

> { [key: string]: any; } getRepoRepository(owner, repo)

Fetch a single repository.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { GetRepoRepositoryRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies GetRepoRepositoryRequest;

  try {
    const data = await api.getRepoRepository(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Repository. |  -  |
| **401** | Caller is not authenticated. |  -  |
| **404** | Not found or no access. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## linkRepoTask

> { [key: string]: any; } linkRepoTask(owner, repo, linkRepoTaskRequest)

Link an existing Spatio task to this repo, allocating a per-repo number.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { LinkRepoTaskOperationRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // LinkRepoTaskRequest
    linkRepoTaskRequest: ...,
  } satisfies LinkRepoTaskOperationRequest;

  try {
    const data = await api.linkRepoTask(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **linkRepoTaskRequest** | [LinkRepoTaskRequest](LinkRepoTaskRequest.md) |  | |

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
| **200** | Idempotent re-link, returns the existing number. |  -  |
| **201** | Created link with the allocated number. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRepoBranches

> { [key: string]: any; } listRepoBranches(owner, repo)

List branches on a repository.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { ListRepoBranchesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies ListRepoBranchesRequest;

  try {
    const data = await api.listRepoBranches(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Branch envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRepoCommits

> { [key: string]: any; } listRepoCommits(owner, repo, branch, limit)

List commits on a repository.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { ListRepoCommitsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // string (optional)
    branch: branch_example,
    // number (optional)
    limit: 56,
  } satisfies ListRepoCommitsRequest;

  try {
    const data = await api.listRepoCommits(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **branch** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Commit envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRepoPullRequests

> { [key: string]: any; } listRepoPullRequests(owner, repo)

List pull requests on a repository.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { ListRepoPullRequestsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies ListRepoPullRequestsRequest;

  try {
    const data = await api.listRepoPullRequests(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | PR envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRepoRepositories

> { [key: string]: any; } listRepoRepositories(visibility, limit)

List the caller\&#39;s accessible repositories.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { ListRepoRepositoriesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string (optional)
    visibility: visibility_example,
    // number (optional)
    limit: 56,
  } satisfies ListRepoRepositoriesRequest;

  try {
    const data = await api.listRepoRepositories(body);
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
| **visibility** | `string` |  | [Optional] [Defaults to `undefined`] |
| **limit** | `number` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Repository envelope (provider-tied shape). |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRepoTasks

> { [key: string]: any; } listRepoTasks(owner, repo, state, perPage, page)

List tasks linked to this repo (the \&quot;issues\&quot; surface).

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { ListRepoTasksRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // 'open' | 'closed' | 'all' (optional)
    state: state_example,
    // number (optional)
    perPage: 56,
    // number (optional)
    page: 56,
  } satisfies ListRepoTasksRequest;

  try {
    const data = await api.listRepoTasks(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **state** | `open`, `closed`, `all` |  | [Optional] [Defaults to `undefined`] [Enum: open, closed, all] |
| **perPage** | `number` |  | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Linked-task envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRepoWorkflows

> { [key: string]: any; } listRepoWorkflows(owner, repo)

List CI workflows.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { ListRepoWorkflowsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies ListRepoWorkflowsRequest;

  try {
    const data = await api.listRepoWorkflows(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Workflow envelope. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## mergeRepoPullRequest

> { [key: string]: any; } mergeRepoPullRequest(owner, repo, number, requestBody)

Merge a pull request.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { MergeRepoPullRequestRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // number
    number: 56,
    // { [key: string]: any; } (optional)
    requestBody: Object,
  } satisfies MergeRepoPullRequestRequest;

  try {
    const data = await api.mergeRepoPullRequest(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **number** | `number` |  | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` |  | [Optional] |

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
| **200** | Merge result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## triggerRepoWorkflow

> { [key: string]: any; } triggerRepoWorkflow(owner, repo, id, requestBody)

Trigger a workflow_dispatch run.

### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { TriggerRepoWorkflowRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // string
    id: id_example,
    // { [key: string]: any; } (optional)
    requestBody: Object,
  } satisfies TriggerRepoWorkflowRequest;

  try {
    const data = await api.triggerRepoWorkflow(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **id** | `string` |  | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` |  | [Optional] |

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
| **200** | Trigger result. |  -  |
| **401** | Caller is not authenticated. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceCreateRepoBranch

> { [key: string]: any; } workspaceCreateRepoBranch(org, workspace, owner, repo, requestBody)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCreateRepoBranchRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateRepoBranchRequest;

  try {
    const data = await api.workspaceCreateRepoBranch(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
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


## workspaceCreateRepoPullRequest

> { [key: string]: any; } workspaceCreateRepoPullRequest(org, workspace, owner, repo, requestBody)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCreateRepoPullRequestRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateRepoPullRequestRequest;

  try {
    const data = await api.workspaceCreateRepoPullRequest(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
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


## workspaceCreateRepoRepository

> { [key: string]: any; } workspaceCreateRepoRepository(org, workspace, requestBody)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceCreateRepoRepositoryRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceCreateRepoRepositoryRequest;

  try {
    const data = await api.workspaceCreateRepoRepository(body);
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


## workspaceGetRepoCommit

> { [key: string]: any; } workspaceGetRepoCommit(org, workspace, owner, repo, sha)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetRepoCommitRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // string
    sha: sha_example,
  } satisfies WorkspaceGetRepoCommitRequest;

  try {
    const data = await api.workspaceGetRepoCommit(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **sha** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Commit |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceGetRepoRepository

> { [key: string]: any; } workspaceGetRepoRepository(org, workspace, owner, repo)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceGetRepoRepositoryRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies WorkspaceGetRepoRepositoryRequest;

  try {
    const data = await api.workspaceGetRepoRepository(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Repo |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |
| **404** | Not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceLinkRepoTask

> { [key: string]: any; } workspaceLinkRepoTask(org, workspace, owner, repo, requestBody)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceLinkRepoTaskRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // { [key: string]: any; }
    requestBody: Object,
  } satisfies WorkspaceLinkRepoTaskRequest;

  try {
    const data = await api.workspaceLinkRepoTask(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Idempotent |  -  |
| **201** | Created |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListRepoBranches

> { [key: string]: any; } workspaceListRepoBranches(org, workspace, owner, repo)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListRepoBranchesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies WorkspaceListRepoBranchesRequest;

  try {
    const data = await api.workspaceListRepoBranches(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Branches |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListRepoCommits

> { [key: string]: any; } workspaceListRepoCommits(org, workspace, owner, repo)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListRepoCommitsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies WorkspaceListRepoCommitsRequest;

  try {
    const data = await api.workspaceListRepoCommits(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Commits |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListRepoPullRequests

> { [key: string]: any; } workspaceListRepoPullRequests(org, workspace, owner, repo)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListRepoPullRequestsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies WorkspaceListRepoPullRequestsRequest;

  try {
    const data = await api.workspaceListRepoPullRequests(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | PRs |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListRepoRepositories

> { [key: string]: any; } workspaceListRepoRepositories(org, workspace)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListRepoRepositoriesRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
  } satisfies WorkspaceListRepoRepositoriesRequest;

  try {
    const data = await api.workspaceListRepoRepositories(body);
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
| **200** | Repos |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListRepoTasks

> { [key: string]: any; } workspaceListRepoTasks(org, workspace, owner, repo)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListRepoTasksRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies WorkspaceListRepoTasksRequest;

  try {
    const data = await api.workspaceListRepoTasks(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Linked tasks |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceListRepoWorkflows

> { [key: string]: any; } workspaceListRepoWorkflows(org, workspace, owner, repo)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceListRepoWorkflowsRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
  } satisfies WorkspaceListRepoWorkflowsRequest;

  try {
    const data = await api.workspaceListRepoWorkflows(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Workflows |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceMergeRepoPullRequest

> { [key: string]: any; } workspaceMergeRepoPullRequest(org, workspace, owner, repo, number, requestBody)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceMergeRepoPullRequestRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // number
    number: 56,
    // { [key: string]: any; } (optional)
    requestBody: Object,
  } satisfies WorkspaceMergeRepoPullRequestRequest;

  try {
    const data = await api.workspaceMergeRepoPullRequest(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **number** | `number` |  | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` |  | [Optional] |

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
| **200** | Merged |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## workspaceTriggerRepoWorkflow

> { [key: string]: any; } workspaceTriggerRepoWorkflow(org, workspace, owner, repo, id, requestBody)



### Example

```ts
import {
  Configuration,
  RepoApi,
} from '@spatio/sdk-ts';
import type { WorkspaceTriggerRepoWorkflowRequest } from '@spatio/sdk-ts';

async function example() {
  console.log("🚀 Testing @spatio/sdk-ts SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RepoApi(config);

  const body = {
    // string
    org: org_example,
    // string
    workspace: workspace_example,
    // string
    owner: owner_example,
    // string
    repo: repo_example,
    // string
    id: id_example,
    // { [key: string]: any; } (optional)
    requestBody: Object,
  } satisfies WorkspaceTriggerRepoWorkflowRequest;

  try {
    const data = await api.workspaceTriggerRepoWorkflow(body);
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
| **owner** | `string` |  | [Defaults to `undefined`] |
| **repo** | `string` |  | [Defaults to `undefined`] |
| **id** | `string` |  | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` |  | [Optional] |

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
| **200** | Triggered |  -  |
| **401** | Unauthenticated |  -  |
| **403** | Insufficient permission |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

