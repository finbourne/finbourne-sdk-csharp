# Finbourne.Sdk.Workflow.Api.WorkersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWorker**](#createworker) | **POST** `/workflow/api/workers` | CreateWorker: Create a new Worker |
| [**DeleteWorker**](#deleteworker) | **DELETE** `/workflow/api/workers/{scope}/{code}` | DeleteWorker: Delete a Worker |
| [**GetWorker**](#getworker) | **GET** `/workflow/api/workers/{scope}/{code}` | GetWorker: Get a Worker |
| [**GetWorkerResult**](#getworkerresult) | **GET** `/workflow/api/workers/{runId}/$result` | GetWorkerResult: Get the status of a specific run of a worker with any relevant results |
| [**ListWorkers**](#listworkers) | **GET** `/workflow/api/workers` | ListWorkers: List Workers |
| [**RunWorker**](#runworker) | **POST** `/workflow/api/workers/{scope}/{code}/$run` | RunWorker: Run a Worker |
| [**UpdateWorker**](#updateworker) | **PUT** `/workflow/api/workers/{scope}/{code}` | UpdateWorker: Update a Worker |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<WorkersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
```

---

<a id="createworker"></a>
## CreateWorker

> Worker CreateWorker(CreateWorkerRequest createWorkerRequest)

CreateWorker: Create a new Worker

If the Worker already exists a failure will be returned

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
var createWorkerRequest = new CreateWorkerRequest(); // CreateWorkerRequest
Worker result = apiInstance.CreateWorker(createWorkerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createWorkerRequest** | [CreateWorkerRequest](CreateWorkerRequest.md) | body | **required** | Worker to be created |

### Return type

[Worker](Worker.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateWorkerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Worker> response = apiInstance.CreateWorkerWithHttpInfo(createWorkerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteworker"></a>
## DeleteWorker

> DeletedEntityResponse DeleteWorker(string scope, string code)

DeleteWorker: Delete a Worker

If the Worker does not exist a failure will be returned

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteWorker(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the worker to be deleted |
| **code** | **string** | path | **required** | Code of the worker to be deleted |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Worker not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteWorkerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteWorkerWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getworker"></a>
## GetWorker

> Worker GetWorker(string scope, string code, DateTimeOffset? asAt = null)

GetWorker: Get a Worker

Will return a NotFound failure if the Worker does not exist

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Worker result = apiInstance.GetWorker(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the worker |
| **code** | **string** | path | **required** | Code of the worker |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Worker. Defaults to returning the latest version of the Worker if not specified. |

### Return type

[Worker](Worker.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetWorkerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Worker> response = apiInstance.GetWorkerWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getworkerresult"></a>
## GetWorkerResult

> GetWorkerResultResponse GetWorkerResult(Guid runId)

GetWorkerResult: Get the status of a specific run of a worker with any relevant results

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
var runId = "runId_example";  // Guid
GetWorkerResultResponse result = apiInstance.GetWorkerResult(runId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **Guid** | path | **required** | The ID returned when calling Run Worker |

### Return type

[GetWorkerResultResponse](GetWorkerResultResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetWorkerResultWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetWorkerResultResponse> response = apiInstance.GetWorkerResultWithHttpInfo(runId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listworkers"></a>
## ListWorkers

> PagedResourceListOfWorker ListWorkers(DateTimeOffset? asAt = null, string? filter = null, List<string>? sortBy = null, int? limit = null, string? page = null)

ListWorkers: List Workers

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 10;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfWorker result = apiInstance.ListWorkers(asAt, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Workers. Defaults to return the latest version of each Worker if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here: https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each optionally suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Default: `10` |
| **page** | **string?** | query | optional | The pagination token to use to continue listing workers from a previous call to list workers. This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfWorker](PagedResourceListOfWorker.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListWorkersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfWorker> response = apiInstance.ListWorkersWithHttpInfo(asAt, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runworker"></a>
## RunWorker

> RunWorkerResponse RunWorker(string scope, string code, RunWorkerRequest runWorkerRequest, DateTimeOffset? asAt = null)

RunWorker: Run a Worker

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var runWorkerRequest = new RunWorkerRequest(); // RunWorkerRequest
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
RunWorkerResponse result = apiInstance.RunWorker(scope, code, runWorkerRequest, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the worker |
| **code** | **string** | path | **required** | Code of the worker |
| **runWorkerRequest** | [RunWorkerRequest](RunWorkerRequest.md) | body | **required** |  |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Worker. Defaults to returning the latest version of the Worker if not specified. |

### Return type

[RunWorkerResponse](RunWorkerResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunWorkerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RunWorkerResponse> response = apiInstance.RunWorkerWithHttpInfo(scope, code, runWorkerRequest, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateworker"></a>
## UpdateWorker

> Worker UpdateWorker(string scope, string code, UpdateWorkerRequest updateWorkerRequest)

UpdateWorker: Update a Worker

If the Worker does not exist a failure will be returned

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateWorkerRequest = new UpdateWorkerRequest(); // UpdateWorkerRequest
Worker result = apiInstance.UpdateWorker(scope, code, updateWorkerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the worker to be updated |
| **code** | **string** | path | **required** | Code of the worker to be updated |
| **updateWorkerRequest** | [UpdateWorkerRequest](UpdateWorkerRequest.md) | body | **required** | State of the updated worker |

### Return type

[Worker](Worker.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Worker not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateWorkerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Worker> response = apiInstance.UpdateWorkerWithHttpInfo(scope, code, updateWorkerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

