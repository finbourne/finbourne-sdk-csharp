# Finbourne.Sdk.Horizon.Api.RunsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelInstance**](#cancelinstance) | **PUT** `/horizon/api/runs/cancel` | [EXPERIMENTAL] CancelInstance: Cancels multiple instance executions. |
| [**GetRunResults**](#getrunresults) | **GET** `/horizon/api/runs` | [EXPERIMENTAL] GetRunResults: Get run results |
| [**RerunInstance**](#reruninstance) | **PUT** `/horizon/api/runs/{runId}/rerun` | [EXPERIMENTAL] RerunInstance: Reruns a single instance execution. |
| [**StopInstanceExecution**](#stopinstanceexecution) | **PUT** `/horizon/api/runs/{instanceId}/{runId}/stop` | [EXPERIMENTAL] StopInstanceExecution: Stops a single instance execution. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Horizon.Api;
using Finbourne.Sdk.Horizon.Client;
using Finbourne.Sdk.Horizon.Extensions;
using Finbourne.Sdk.Services.Horizon.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RunsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RunsApi>();
```

---

<a id="cancelinstance"></a>
## CancelInstance

> IntegrationCancellationResponse CancelInstance(CancelRunRequest cancelRunRequest)

[EXPERIMENTAL] CancelInstance: Cancels multiple instance executions.

Cancels multiple execution instances of an integration. The execution instance must be queued, the user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RunsApi>();
var cancelRunRequest = new CancelRunRequest(); // CancelRunRequest
IntegrationCancellationResponse result = apiInstance.CancelInstance(cancelRunRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **cancelRunRequest** | [CancelRunRequest](CancelRunRequest.md) | body | **required** | Contains the run identifiers and a message to be set e.g. \&quot;b64135e7-98a0-41af-a845-d86167d54cc7\&quot;. |

### Return type

[IntegrationCancellationResponse](IntegrationCancellationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Some or all of the instances requested were cancelled. |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | None of the executions does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CancelInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IntegrationCancellationResponse> response = apiInstance.CancelInstanceWithHttpInfo(cancelRunRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrunresults"></a>
## GetRunResults

> PagedResourceListOfIntegrationRunResponse GetRunResults(string? filter = null, List<string>? sortBy = null, int? limit = null, string? pageToken = null)

[EXPERIMENTAL] GetRunResults: Get run results

Get run results

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RunsApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 100;  // int? (optional)
var pageToken = "\"\"";  // string? (optional)
PagedResourceListOfIntegrationRunResponse result = apiInstance.GetRunResults(filter, sortBy, limit, pageToken);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Default: `100` |
| **pageToken** | **string?** | query | optional | The pagination token to use to continue listing integration runs; this value is returned from             the previous call. If a pagination token is provided, the &lt;i&gt;sortBy&lt;/i&gt; and &lt;i&gt;filter&lt;/i&gt; fields must not have changed since the original request. Default: `&quot;&quot;` |

### Return type

[PagedResourceListOfIntegrationRunResponse](PagedResourceListOfIntegrationRunResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Not Found |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRunResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfIntegrationRunResponse> response = apiInstance.GetRunResultsWithHttpInfo(filter, sortBy, limit, pageToken);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reruninstance"></a>
## RerunInstance

> IntegrationRerunResponse RerunInstance(string runId)

[EXPERIMENTAL] RerunInstance: Reruns a single instance execution.

Reruns an execution instance of an integration. The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RunsApi>();
var runId = "runId_example";  // string
IntegrationRerunResponse result = apiInstance.RerunInstance(runId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | Run identifier e.g. \&quot;b64135e7-98a0-41af-a845-d86167d54cc7\&quot;. |

### Return type

[IntegrationRerunResponse](IntegrationRerunResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The instance was rerun. |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The execution does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RerunInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IntegrationRerunResponse> response = apiInstance.RerunInstanceWithHttpInfo(runId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="stopinstanceexecution"></a>
## StopInstanceExecution

> Object StopInstanceExecution(string instanceId, string runId)

[EXPERIMENTAL] StopInstanceExecution: Stops a single instance execution.

Stops an execution instance of an External Client Application integration type. The execution instance must be started, the user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RunsApi>();
var instanceId = "instanceId_example";  // string
var runId = "runId_example";  // string
Object result = apiInstance.StopInstanceExecution(instanceId, runId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** |  |
| **runId** | **string** | path | **required** | Run identifier e.g. \&quot;b64135e7-98a0-41af-a845-d86167d54cc7\&quot;. |

### Return type

**Object**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The instance was stopped. |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The execution does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the StopInstanceExecutionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Object> response = apiInstance.StopInstanceExecutionWithHttpInfo(instanceId, runId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

