# Finbourne.Sdk.Lusid.Api.WorkspaceApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateItem**](#createitem) | **POST** `/api/api/workspaces/{visibility}/{workspaceName}/items` | [EXPERIMENTAL] CreateItem: Create a new item in a workspace. |
| [**CreateWorkspace**](#createworkspace) | **POST** `/api/api/workspaces/{visibility}` | [EXPERIMENTAL] CreateWorkspace: Create a new workspace. |
| [**DeleteItem**](#deleteitem) | **DELETE** `/api/api/workspaces/{visibility}/{workspaceName}/items/{groupName}/{itemName}` | [EXPERIMENTAL] DeleteItem: Delete an item from a workspace. |
| [**DeleteWorkspace**](#deleteworkspace) | **DELETE** `/api/api/workspaces/{visibility}/{workspaceName}` | [EXPERIMENTAL] DeleteWorkspace: Delete a workspace. |
| [**GetItem**](#getitem) | **GET** `/api/api/workspaces/{visibility}/{workspaceName}/items/{groupName}/{itemName}` | [EXPERIMENTAL] GetItem: Get a single workspace item. |
| [**GetWorkspace**](#getworkspace) | **GET** `/api/api/workspaces/{visibility}/{workspaceName}` | [EXPERIMENTAL] GetWorkspace: Get a workspace. |
| [**ListItems**](#listitems) | **GET** `/api/api/workspaces/{visibility}/{workspaceName}/items` | [EXPERIMENTAL] ListItems: List the items in a workspace. |
| [**ListWorkspaces**](#listworkspaces) | **GET** `/api/api/workspaces/{visibility}` | [EXPERIMENTAL] ListWorkspaces: List workspaces. |
| [**SearchItems**](#searchitems) | **GET** `/api/api/workspaces/{visibility}/items` | [EXPERIMENTAL] SearchItems: List items across all workspaces. |
| [**UpdateItem**](#updateitem) | **PUT** `/api/api/workspaces/{visibility}/{workspaceName}/items/{groupName}/{itemName}` | [EXPERIMENTAL] UpdateItem: Update an item in a workspace. |
| [**UpdateWorkspace**](#updateworkspace) | **PUT** `/api/api/workspaces/{visibility}/{workspaceName}` | [EXPERIMENTAL] UpdateWorkspace: Update a workspace. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Lusid.Api;
using Finbourne.Sdk.Lusid.Client;
using Finbourne.Sdk.Lusid.Extensions;
using Finbourne.Sdk.Services.Lusid.Model;
using Newtonsoft.Json;

// Use the ApiFactoryBuilder to build an instance of the API class.
// Credentials are loaded from the secrets.json file by default.
// See https://support.lusid.com/knowledgebase/article/KA-01667 for details.

var secretsFilename = "secrets.json";
var path = Path.Combine(Directory.GetCurrentDirectory(), secretsFilename);
// Replace with the relevant values
File.WriteAllText(
    path,
    @"{
        ""api"": {
            ""tokenUrl"": ""<your-token-url>"",
            ""baseUrl"": ""https://<your-domain>.lusid.com"",
            ""username"": ""<your-username>"",
            ""password"": ""<your-password>"",
            ""clientId"": ""<your-client-id>"",
            ""clientSecret"": ""<your-client-secret>""
        }
    }");

// uncomment the below to use configuration overrides
// var opts = new ConfigurationOptions();
// opts.TimeoutMs = 30_000;

// uncomment the below to use an api factory with overrides
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<WorkspaceApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
```

---

<a id="createitem"></a>
## CreateItem

> WorkspaceItem CreateItem(string visibility, string workspaceName, WorkspaceItemCreationRequest? workspaceItemCreationRequest = null)

[EXPERIMENTAL] CreateItem: Create a new item in a workspace.

Create a new item in a workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var workspaceItemCreationRequest = new WorkspaceItemCreationRequest?(); // WorkspaceItemCreationRequest? (optional)
WorkspaceItem result = apiInstance.CreateItem(visibility, workspaceName, workspaceItemCreationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the containing workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The item&#39;s workspace name. |
| **workspaceItemCreationRequest** | [WorkspaceItemCreationRequest?](WorkspaceItemCreationRequest?.md) | body | optional | The item to be created. |

### Return type

[WorkspaceItem](WorkspaceItem.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The workspace item created. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateItemWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WorkspaceItem> response = apiInstance.CreateItemWithHttpInfo(visibility, workspaceName, workspaceItemCreationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createworkspace"></a>
## CreateWorkspace

> Workspace CreateWorkspace(string visibility, WorkspaceCreationRequest? workspaceCreationRequest = null)

[EXPERIMENTAL] CreateWorkspace: Create a new workspace.

Create a new workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceCreationRequest = new WorkspaceCreationRequest?(); // WorkspaceCreationRequest? (optional)
Workspace result = apiInstance.CreateWorkspace(visibility, workspaceCreationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the workspace being created. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceCreationRequest** | [WorkspaceCreationRequest?](WorkspaceCreationRequest?.md) | body | optional | The workspace to be created. |

### Return type

[Workspace](Workspace.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The workspace created. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateWorkspaceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Workspace> response = apiInstance.CreateWorkspaceWithHttpInfo(visibility, workspaceCreationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteitem"></a>
## DeleteItem

> DeletedEntityResponse DeleteItem(string visibility, string workspaceName, string groupName, string itemName)

[EXPERIMENTAL] DeleteItem: Delete an item from a workspace.

Delete an item from a workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var groupName = "groupName_example";  // string
var itemName = "itemName_example";  // string
DeletedEntityResponse result = apiInstance.DeleteItem(visibility, workspaceName, groupName, itemName);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the containing workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The name of the workspace. |
| **groupName** | **string** | path | **required** | The group containing the item. |
| **itemName** | **string** | path | **required** | The name of the item. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The result of deleting a workspace item. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteItemWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteItemWithHttpInfo(visibility, workspaceName, groupName, itemName);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteworkspace"></a>
## DeleteWorkspace

> DeletedEntityResponse DeleteWorkspace(string visibility, string workspaceName, bool? recurse = null)

[EXPERIMENTAL] DeleteWorkspace: Delete a workspace.

Delete a workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var recurse = false;  // bool? (optional)
DeletedEntityResponse result = apiInstance.DeleteWorkspace(visibility, workspaceName, recurse);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The name of the workspace. |
| **recurse** | **bool?** | query | optional | If true, recursively delete items in the workspace. Default: `false` |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The result of deleting a workspace. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteWorkspaceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteWorkspaceWithHttpInfo(visibility, workspaceName, recurse);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getitem"></a>
## GetItem

> WorkspaceItem GetItem(string visibility, string workspaceName, string groupName, string itemName, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetItem: Get a single workspace item.

Get a single workspace item.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var groupName = "groupName_example";  // string
var itemName = "itemName_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
WorkspaceItem result = apiInstance.GetItem(visibility, workspaceName, groupName, itemName, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the containing workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The name of the workspace. |
| **groupName** | **string** | path | **required** | The group containing the item. |
| **itemName** | **string** | path | **required** | The name of the item. |
| **asAt** | **DateTimeOffset?** | query | optional | The datetime at which to request the workspace item. If not provided, defaults to &#39;latest&#39;. |

### Return type

[WorkspaceItem](WorkspaceItem.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The workspace item requested. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetItemWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WorkspaceItem> response = apiInstance.GetItemWithHttpInfo(visibility, workspaceName, groupName, itemName, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getworkspace"></a>
## GetWorkspace

> Workspace GetWorkspace(string visibility, string workspaceName, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetWorkspace: Get a workspace.

Get a workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Workspace result = apiInstance.GetWorkspace(visibility, workspaceName, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The workspace name. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve workspaces. Defaults to &#39;latest&#39; if not specified. |

### Return type

[Workspace](Workspace.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The workspace. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetWorkspaceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Workspace> response = apiInstance.GetWorkspaceWithHttpInfo(visibility, workspaceName, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listitems"></a>
## ListItems

> PagedResourceListOfWorkspaceItem ListItems(string visibility, string workspaceName, DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListItems: List the items in a workspace.

List the items in a workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfWorkspaceItem result = apiInstance.ListItems(visibility, workspaceName, asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the containing workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The item&#39;s workspace name. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve workspace items. Defaults to &#39;latest&#39; if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing workspaces items from a previous call to list workspaces items.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfWorkspaceItem](PagedResourceListOfWorkspaceItem.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The items in a workspace. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListItemsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfWorkspaceItem> response = apiInstance.ListItemsWithHttpInfo(visibility, workspaceName, asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listworkspaces"></a>
## ListWorkspaces

> PagedResourceListOfWorkspace ListWorkspaces(string visibility, DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListWorkspaces: List workspaces.

List workspaces.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfWorkspace result = apiInstance.ListWorkspaces(visibility, asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the workspaces. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve workspaces. Defaults to &#39;latest&#39; if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing workspaces from a previous call to list workspaces.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfWorkspace](PagedResourceListOfWorkspace.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The workspaces. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListWorkspacesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfWorkspace> response = apiInstance.ListWorkspacesWithHttpInfo(visibility, asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="searchitems"></a>
## SearchItems

> PagedResourceListOfItemAndWorkspace SearchItems(string visibility, DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] SearchItems: List items across all workspaces.

List items across all workspaces.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfItemAndWorkspace result = apiInstance.SearchItems(visibility, asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the containing workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve workspace items. Defaults to &#39;latest&#39; if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing workspaces items from a previous call to list workspaces items.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfItemAndWorkspace](PagedResourceListOfItemAndWorkspace.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Items across all workspaces. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SearchItemsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfItemAndWorkspace> response = apiInstance.SearchItemsWithHttpInfo(visibility, asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateitem"></a>
## UpdateItem

> WorkspaceItem UpdateItem(string visibility, string workspaceName, string groupName, string itemName, WorkspaceItemUpdateRequest? workspaceItemUpdateRequest = null)

[EXPERIMENTAL] UpdateItem: Update an item in a workspace.

Update an item in a workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var groupName = "groupName_example";  // string
var itemName = "itemName_example";  // string
var workspaceItemUpdateRequest = new WorkspaceItemUpdateRequest?(); // WorkspaceItemUpdateRequest? (optional)
WorkspaceItem result = apiInstance.UpdateItem(visibility, workspaceName, groupName, itemName, workspaceItemUpdateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the containing workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The workspace name. |
| **groupName** | **string** | path | **required** | The group containing the item. |
| **itemName** | **string** | path | **required** | The item name. |
| **workspaceItemUpdateRequest** | [WorkspaceItemUpdateRequest?](WorkspaceItemUpdateRequest?.md) | body | optional | The new item details. |

### Return type

[WorkspaceItem](WorkspaceItem.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The workspace item updated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateItemWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WorkspaceItem> response = apiInstance.UpdateItemWithHttpInfo(visibility, workspaceName, groupName, itemName, workspaceItemUpdateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateworkspace"></a>
## UpdateWorkspace

> Workspace UpdateWorkspace(string visibility, string workspaceName, WorkspaceUpdateRequest? workspaceUpdateRequest = null)

[EXPERIMENTAL] UpdateWorkspace: Update a workspace.

Update a workspace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkspaceApi>();
var visibility = "shared";  // string
var workspaceName = "workspaceName_example";  // string
var workspaceUpdateRequest = new WorkspaceUpdateRequest?(); // WorkspaceUpdateRequest? (optional)
Workspace result = apiInstance.UpdateWorkspace(visibility, workspaceName, workspaceUpdateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **visibility** | **string** | path | **required** | The visibility for the workspace. Must be &#x60;shared&#x60; or &#x60;personal&#x60;; case is important. |
| **workspaceName** | **string** | path | **required** | The workspace name. |
| **workspaceUpdateRequest** | [WorkspaceUpdateRequest?](WorkspaceUpdateRequest?.md) | body | optional | The new workspace details. |

### Return type

[Workspace](Workspace.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The workspace updated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateWorkspaceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Workspace> response = apiInstance.UpdateWorkspaceWithHttpInfo(visibility, workspaceName, workspaceUpdateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

