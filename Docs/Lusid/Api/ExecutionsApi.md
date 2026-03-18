# Finbourne.Sdk.Lusid.Api.ExecutionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteExecution**](#deleteexecution) | **DELETE** `/api/api/executions/{scope}/{code}` | [EARLY ACCESS] DeleteExecution: Delete execution |
| [**GetExecution**](#getexecution) | **GET** `/api/api/executions/{scope}/{code}` | [EARLY ACCESS] GetExecution: Get Execution |
| [**ListExecutions**](#listexecutions) | **GET** `/api/api/executions` | ListExecutions: List Executions |
| [**UpsertExecutions**](#upsertexecutions) | **POST** `/api/api/executions` | UpsertExecutions: Upsert Execution |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ExecutionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExecutionsApi>();
```

---

<a id="deleteexecution"></a>
## DeleteExecution

> DeletedEntityResponse DeleteExecution(string scope, string code)

[EARLY ACCESS] DeleteExecution: Delete execution

Delete an execution. Deletion will be valid from the execution's creation datetime.  This means that the execution will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExecutionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteExecution(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The execution scope. |
| **code** | **string** | path | **required** | The execution&#39;s code. This, together with the scope uniquely identifies the execution to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting an execution. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteExecutionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteExecutionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getexecution"></a>
## GetExecution

> Execution GetExecution(string scope, string code, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EARLY ACCESS] GetExecution: Get Execution

Fetch a Execution that matches the specified identifier

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExecutionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Execution result = apiInstance.GetExecution(scope, code, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to which the execution belongs. |
| **code** | **string** | path | **required** | The execution&#39;s unique identifier. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the execution. Defaults to return the latest version of the execution if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Execution\&quot; domain to decorate onto the execution.              These take the format {domain}/{scope}/{code} e.g. \&quot;Execution/system/Name\&quot;. |

### Return type

[Execution](Execution.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The execution matching the given identifier. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetExecutionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Execution> response = apiInstance.GetExecutionWithHttpInfo(scope, code, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listexecutions"></a>
## ListExecutions

> PagedResourceListOfExecution ListExecutions(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

ListExecutions: List Executions

Fetch the last pre-AsAt date version of each execution in scope (does not fetch the entire history).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExecutionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfExecution result = apiInstance.ListExecutions(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the execution. Defaults to return the latest version of the execution if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing execution from a previous call to list executions.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Execution\&quot; domain to decorate onto each execution.                  These take the format {domain}/{scope}/{code} e.g. \&quot;Execution/system/Name\&quot;.                  All properties, except derived properties, are returned by default, without specifying here. |

### Return type

[PagedResourceListOfExecution](PagedResourceListOfExecution.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Executions in scope. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListExecutionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfExecution> response = apiInstance.ListExecutionsWithHttpInfo(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertexecutions"></a>
## UpsertExecutions

> ResourceListOfExecution UpsertExecutions(ExecutionSetRequest? executionSetRequest = null)

UpsertExecutions: Upsert Execution

Upsert; update existing executions with given ids, or create new executions otherwise.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExecutionsApi>();
var executionSetRequest = new ExecutionSetRequest?(); // ExecutionSetRequest? (optional)
ResourceListOfExecution result = apiInstance.UpsertExecutions(executionSetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionSetRequest** | [ExecutionSetRequest?](ExecutionSetRequest?.md) | body | optional | The collection of execution requests. |

### Return type

[ResourceListOfExecution](ResourceListOfExecution.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | A collection of executions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertExecutionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfExecution> response = apiInstance.UpsertExecutionsWithHttpInfo(executionSetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

