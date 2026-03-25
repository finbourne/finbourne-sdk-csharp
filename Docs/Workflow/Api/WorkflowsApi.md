# Finbourne.Sdk.Workflow.Api.WorkflowsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWorkflow**](#createworkflow) | **POST** `/workflow/api/workflows` | CreateWorkflow: Create a new Workflow |
| [**GetWorkflow**](#getworkflow) | **GET** `/workflow/api/workflows/{scope}/{code}` | GetWorkflow: Get a Workflow |

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

