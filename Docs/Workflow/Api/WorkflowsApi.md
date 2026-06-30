# Finbourne.Sdk.Workflow.Api.WorkflowsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWorkflow**](#createworkflow) | **POST** `/workflow/api/workflows` | CreateWorkflow: Create a new Workflow |
| [**DeleteWorkflow**](#deleteworkflow) | **DELETE** `/workflow/api/workflows/{scope}/{code}` | [EXPERIMENTAL] DeleteWorkflow: Delete a Workflow |
| [**GetWorkflow**](#getworkflow) | **GET** `/workflow/api/workflows/{scope}/{code}` | GetWorkflow: Get a Workflow |
| [**ListWorkflows**](#listworkflows) | **GET** `/workflow/api/workflows` | ListWorkflows: List Workflows |
| [**UpdateWorkflow**](#updateworkflow) | **PUT** `/workflow/api/workflows/{scope}/{code}` | [EXPERIMENTAL] UpdateWorkflow: Update an existing Workflow |
| [**UpsertWorkflowProperties**](#upsertworkflowproperties) | **POST** `/workflow/api/workflows/{scope}/{code}/properties` | [EXPERIMENTAL] UpsertWorkflowProperties: Add, update and remove properties on an existing Workflow in bulk. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<WorkflowsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkflowsApi>();
```

---

<a id="createworkflow"></a>
## CreateWorkflow

> WorkflowResponse CreateWorkflow(CreateWorkflowRequest createWorkflowRequest)

CreateWorkflow: Create a new Workflow

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkflowsApi>();
var createWorkflowRequest = new CreateWorkflowRequest(); // CreateWorkflowRequest
WorkflowResponse result = apiInstance.CreateWorkflow(createWorkflowRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createWorkflowRequest** | [CreateWorkflowRequest](CreateWorkflowRequest.md) | body | **required** | The data to create a Workflow |

### Return type

[WorkflowResponse](WorkflowResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **409** | Workflow already exists. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateWorkflowWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WorkflowResponse> response = apiInstance.CreateWorkflowWithHttpInfo(createWorkflowRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteworkflow"></a>
## DeleteWorkflow

> DeletedEntityResponse DeleteWorkflow(string scope, string code)

[EXPERIMENTAL] DeleteWorkflow: Delete a Workflow

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkflowsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteWorkflow(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Workflow |
| **code** | **string** | path | **required** | The code that identifies a Workflow |

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
| **404** | Workflow not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteWorkflowWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteWorkflowWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getworkflow"></a>
## GetWorkflow

> WorkflowResponse GetWorkflow(string scope, string code, DateTimeOffset? asAt = null)

GetWorkflow: Get a Workflow

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkflowsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
WorkflowResponse result = apiInstance.GetWorkflow(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Workflow |
| **code** | **string** | path | **required** | The code that identifies a Workflow |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Workflow. Defaults to returning the latest version if not specified. |

### Return type

[WorkflowResponse](WorkflowResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Workflow not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetWorkflowWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WorkflowResponse> response = apiInstance.GetWorkflowWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listworkflows"></a>
## ListWorkflows

> PagedResourceListOfWorkflowResponse ListWorkflows(DateTimeOffset? asAt = null, string? filter = null, List<string>? sortBy = null, int? limit = null, string? page = null)

ListWorkflows: List Workflows

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkflowsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 10;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfWorkflowResponse result = apiInstance.ListWorkflows(asAt, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Workflows. Defaults to return the latest version of each Workflow if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here: https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Default: `10` |
| **page** | **string?** | query | optional | The pagination token to use to continue listing workflows from a previous call to list workflows. This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfWorkflowResponse](PagedResourceListOfWorkflowResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No Workflows found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListWorkflowsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfWorkflowResponse> response = apiInstance.ListWorkflowsWithHttpInfo(asAt, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateworkflow"></a>
## UpdateWorkflow

> WorkflowResponse UpdateWorkflow(string scope, string code, UpdateWorkflowRequest updateWorkflowRequest)

[EXPERIMENTAL] UpdateWorkflow: Update an existing Workflow

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkflowsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateWorkflowRequest = new UpdateWorkflowRequest(); // UpdateWorkflowRequest
WorkflowResponse result = apiInstance.UpdateWorkflow(scope, code, updateWorkflowRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Workflow |
| **code** | **string** | path | **required** | The code that identifies a Workflow |
| **updateWorkflowRequest** | [UpdateWorkflowRequest](UpdateWorkflowRequest.md) | body | **required** | The data to update a Workflow |

### Return type

[WorkflowResponse](WorkflowResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Workflow not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateWorkflowWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WorkflowResponse> response = apiInstance.UpdateWorkflowWithHttpInfo(scope, code, updateWorkflowRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertworkflowproperties"></a>
## UpsertWorkflowProperties

> BatchUpsertWorkflowPropertiesResponse UpsertWorkflowProperties(string scope, string code, Dictionary<string, PerpetualProperty> requestBody, string? successMode = null)

[EXPERIMENTAL] UpsertWorkflowProperties: Add, update and remove properties on an existing Workflow in bulk.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WorkflowsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, PerpetualProperty>(); // Dictionary<string, PerpetualProperty>
var successMode = "\"Partial\"";  // string? (optional)
BatchUpsertWorkflowPropertiesResponse result = apiInstance.UpsertWorkflowProperties(scope, code, requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a Workflow |
| **code** | **string** | path | **required** | The code that identifies a Workflow |
| **requestBody** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | body | **required** | The properties to upsert, keyed by property key. A null value deletes the property. |
| **successMode** | **string?** | query | optional | Whether the batch should fail Atomically or Partially. Defaults to Partial. Default: `&quot;Partial&quot;` |

### Return type

[BatchUpsertWorkflowPropertiesResponse](BatchUpsertWorkflowPropertiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Workflow not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertWorkflowPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertWorkflowPropertiesResponse> response = apiInstance.UpsertWorkflowPropertiesWithHttpInfo(scope, code, requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

