# Finbourne.Sdk.Workflow.Api.TasksApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchUpdateTasks**](#batchupdatetasks) | **PATCH** `/workflow/api/tasks/$update` | [EXPERIMENTAL] BatchUpdateTasks: Batch update tasks |
| [**CreateTask**](#createtask) | **POST** `/workflow/api/tasks` | CreateTask: Create a new Task |
| [**DeleteTask**](#deletetask) | **DELETE** `/workflow/api/tasks/{id}` | DeleteTask: Delete a Task |
| [**DeleteTasks**](#deletetasks) | **POST** `/workflow/api/tasks/$delete` | DeleteTasks: Batch Delete Tasks |
| [**GetTask**](#gettask) | **GET** `/workflow/api/tasks/{id}` | GetTask: Get a Task |
| [**GetTaskHistory**](#gettaskhistory) | **GET** `/workflow/api/tasks/{id}/history` | GetTaskHistory: Get the history of a Task |
| [**ListTasks**](#listtasks) | **GET** `/workflow/api/tasks` | ListTasks: List Tasks |
| [**UpdateTask**](#updatetask) | **POST** `/workflow/api/tasks/{id}` | UpdateTask: Update a Task |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Workflow.Api;
using Finbourne.Sdk.Workflow.Client;
using Finbourne.Sdk.Workflow.Extensions;
using Finbourne.Sdk.Services.Workflow.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TasksApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
```

---

<a id="batchupdatetasks"></a>
## BatchUpdateTasks

> BatchUpdateTasksResponse BatchUpdateTasks(BatchUpdateTasksRequest? batchUpdateTasksRequest = null)

[EXPERIMENTAL] BatchUpdateTasks: Batch update tasks

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var batchUpdateTasksRequest = new BatchUpdateTasksRequest?(); // BatchUpdateTasksRequest? (optional)
BatchUpdateTasksResponse result = apiInstance.BatchUpdateTasks(batchUpdateTasksRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **batchUpdateTasksRequest** | [BatchUpdateTasksRequest?](BatchUpdateTasksRequest?.md) | body | optional | The details of the request |

### Return type

[BatchUpdateTasksResponse](BatchUpdateTasksResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpdateTasksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpdateTasksResponse> response = apiInstance.BatchUpdateTasksWithHttpInfo(batchUpdateTasksRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createtask"></a>
## CreateTask

> Task CreateTask(CreateTaskRequest createTaskRequest, string? trigger = null)

CreateTask: Create a new Task

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var createTaskRequest = new CreateTaskRequest(); // CreateTaskRequest
var trigger = "trigger_example";  // string? (optional)
Task result = apiInstance.CreateTask(createTaskRequest, trigger);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createTaskRequest** | [CreateTaskRequest](CreateTaskRequest.md) | body | **required** | Request to create Task |
| **trigger** | **string?** | query | optional | The name of the Trigger to invoke |

### Return type

[Task](Task.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTaskWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Task> response = apiInstance.CreateTaskWithHttpInfo(createTaskRequest, trigger);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetask"></a>
## DeleteTask

> DeletedEntityResponse DeleteTask(string id)

DeleteTask: Delete a Task

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var id = "id_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTask(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The identifier for the Task to be deleted. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Task not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTaskWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTaskWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetasks"></a>
## DeleteTasks

> DeletedEntityResponse DeleteTasks(DeleteTasksRequest? deleteTasksRequest = null)

DeleteTasks: Batch Delete Tasks

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var deleteTasksRequest = new DeleteTasksRequest?(); // DeleteTasksRequest? (optional)
DeletedEntityResponse result = apiInstance.DeleteTasks(deleteTasksRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **deleteTasksRequest** | [DeleteTasksRequest?](DeleteTasksRequest?.md) | body | optional | Request with the task instance ids to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Task not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTasksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTasksWithHttpInfo(deleteTasksRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettask"></a>
## GetTask

> Task GetTask(string id, DateTimeOffset? asAt = null)

GetTask: Get a Task

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var id = "id_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Task result = apiInstance.GetTask(id, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Id of the Task to retrieve |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Task. Defaults to returning the latest version of the Task if not specified. |

### Return type

[Task](Task.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Task not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTaskWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Task> response = apiInstance.GetTaskWithHttpInfo(id, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettaskhistory"></a>
## GetTaskHistory

> ResourceListOfChangeItem GetTaskHistory(string id, DateTimeOffset? asAt = null)

GetTaskHistory: Get the history of a Task

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var id = "id_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfChangeItem result = apiInstance.GetTaskHistory(id, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The Task Id for which to get the history |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime of the oldest change to retrieve. Defaults to returning the latest version of the Task if not specified. |

### Return type

[ResourceListOfChangeItem](ResourceListOfChangeItem.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Task not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTaskHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfChangeItem> response = apiInstance.GetTaskHistoryWithHttpInfo(id, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtasks"></a>
## ListTasks

> PagedResourceListOfTask ListTasks(DateTimeOffset? asAt = null, string? filter = null, List<string>? sortBy = null, int? limit = null, string? page = null)

ListTasks: List Tasks

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 10;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfTask result = apiInstance.ListTasks(asAt, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Tasks. Defaults to return the latest version of each Task if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here: https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each optionally suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Default: `10` |
| **page** | **string?** | query | optional | The pagination token to use to continue listing tasks from a previous call to list tasks. This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfTask](PagedResourceListOfTask.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No Tasks found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTasksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTask> response = apiInstance.ListTasksWithHttpInfo(asAt, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatetask"></a>
## UpdateTask

> Task UpdateTask(string id, string? trigger = null, UpdateTaskRequest? updateTaskRequest = null)

UpdateTask: Update a Task

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TasksApi>();
var id = "id_example";  // string
var trigger = "trigger_example";  // string? (optional)
var updateTaskRequest = new UpdateTaskRequest?(); // UpdateTaskRequest? (optional)
Task result = apiInstance.UpdateTask(id, trigger, updateTaskRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Id of the Task to act upon |
| **trigger** | **string?** | query | optional |  |
| **updateTaskRequest** | [UpdateTaskRequest?](UpdateTaskRequest?.md) | body | optional | The details of the request |

### Return type

[Task](Task.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Tasks not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateTaskWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Task> response = apiInstance.UpdateTaskWithHttpInfo(id, trigger, updateTaskRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

