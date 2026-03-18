# Finbourne.Sdk.Workflow.Api.TaskDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTaskDefinition**](#createtaskdefinition) | **POST** `/workflow/api/taskdefinitions` | CreateTaskDefinition: Create a new Task Definition |
| [**DeleteTaskDefinition**](#deletetaskdefinition) | **DELETE** `/workflow/api/taskdefinitions/{scope}/{code}` | DeleteTaskDefinition: Delete a Task Definition |
| [**GetTaskDefinition**](#gettaskdefinition) | **GET** `/workflow/api/taskdefinitions/{scope}/{code}` | GetTaskDefinition: Get a Task Definition |
| [**ListTaskDefinitions**](#listtaskdefinitions) | **GET** `/workflow/api/taskdefinitions` | ListTaskDefinitions: List Task Definitions |
| [**ListTasksForTaskDefinition**](#listtasksfortaskdefinition) | **GET** `/workflow/api/taskdefinitions/{scope}/{code}/tasks` | ListTasksForTaskDefinition: List Tasks for a Task Definition |
| [**UpdateTaskDefinition**](#updatetaskdefinition) | **PUT** `/workflow/api/taskdefinitions/{scope}/{code}` | UpdateTaskDefinition: Update an existing Task Definition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TaskDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaskDefinitionsApi>();
```

---

<a id="createtaskdefinition"></a>
## CreateTaskDefinition

> TaskDefinition CreateTaskDefinition(CreateTaskDefinitionRequest createTaskDefinitionRequest)

CreateTaskDefinition: Create a new Task Definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaskDefinitionsApi>();
var createTaskDefinitionRequest = new CreateTaskDefinitionRequest(); // CreateTaskDefinitionRequest
TaskDefinition result = apiInstance.CreateTaskDefinition(createTaskDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createTaskDefinitionRequest** | [CreateTaskDefinitionRequest](CreateTaskDefinitionRequest.md) | body | **required** | The data to create a Task Definition |

### Return type

[TaskDefinition](TaskDefinition.md)

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
<summary>Using the CreateTaskDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaskDefinition> response = apiInstance.CreateTaskDefinitionWithHttpInfo(createTaskDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetaskdefinition"></a>
## DeleteTaskDefinition

> DeletedEntityResponse DeleteTaskDefinition(string scope, string code)

DeleteTaskDefinition: Delete a Task Definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaskDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTaskDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Task Definition |
| **code** | **string** | path | **required** | The code that identifies a Task Definition |

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
| **404** | Task Definition not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTaskDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTaskDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettaskdefinition"></a>
## GetTaskDefinition

> TaskDefinition GetTaskDefinition(string scope, string code, DateTimeOffset? asAt = null)

GetTaskDefinition: Get a Task Definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaskDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
TaskDefinition result = apiInstance.GetTaskDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Task Definition |
| **code** | **string** | path | **required** | The code that identifies a Task Definition |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Task Definition. Defaults to returning the latest version of the Task Definition if not specified. |

### Return type

[TaskDefinition](TaskDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Task Definition not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTaskDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaskDefinition> response = apiInstance.GetTaskDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtaskdefinitions"></a>
## ListTaskDefinitions

> PagedResourceListOfTaskDefinition ListTaskDefinitions(DateTimeOffset? asAt = null, string? filter = null, List<string>? sortBy = null, int? limit = null, string? page = null)

ListTaskDefinitions: List Task Definitions

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaskDefinitionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 10;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfTaskDefinition result = apiInstance.ListTaskDefinitions(asAt, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Task Definitions. Defaults to return the latest version of each Task Definition if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here: https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Default: `10` |
| **page** | **string?** | query | optional | The pagination token to use to continue listing task definitions from a previous call to list task definitions. This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfTaskDefinition](PagedResourceListOfTaskDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of Task Definitions |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No Task Definitions found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTaskDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTaskDefinition> response = apiInstance.ListTaskDefinitionsWithHttpInfo(asAt, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtasksfortaskdefinition"></a>
## ListTasksForTaskDefinition

> ResourceListOfTask ListTasksForTaskDefinition(string scope, string code, DateTimeOffset? asAt = null)

ListTasksForTaskDefinition: List Tasks for a Task Definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaskDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfTask result = apiInstance.ListTasksForTaskDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Task Definition |
| **code** | **string** | path | **required** | The code that identifies a Task Definition |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Tasks. Defaults to return the latest version of each Task if not specified. |

### Return type

[ResourceListOfTask](ResourceListOfTask.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No tasks found for this Task Definition. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTasksForTaskDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTask> response = apiInstance.ListTasksForTaskDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatetaskdefinition"></a>
## UpdateTaskDefinition

> TaskDefinition UpdateTaskDefinition(string scope, string code, UpdateTaskDefinitionRequest updateTaskDefinitionRequest)

UpdateTaskDefinition: Update an existing Task Definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaskDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateTaskDefinitionRequest = new UpdateTaskDefinitionRequest(); // UpdateTaskDefinitionRequest
TaskDefinition result = apiInstance.UpdateTaskDefinition(scope, code, updateTaskDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Task Definition |
| **code** | **string** | path | **required** | The code that identifies a Task Definition |
| **updateTaskDefinitionRequest** | [UpdateTaskDefinitionRequest](UpdateTaskDefinitionRequest.md) | body | **required** | The data to update a Task Definition |

### Return type

[TaskDefinition](TaskDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Task Definition not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateTaskDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaskDefinition> response = apiInstance.UpdateTaskDefinitionWithHttpInfo(scope, code, updateTaskDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

