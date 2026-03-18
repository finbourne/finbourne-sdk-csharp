# Finbourne.Sdk.Horizon.Api.LogsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetIntegrationLogResults**](#getintegrationlogresults) | **GET** `/horizon/api/logs` | [EXPERIMENTAL] GetIntegrationLogResults: Get integration log results |
| [**InsertExternalLogs**](#insertexternallogs) | **POST** `/horizon/api/logs/{instanceid}/{runid}` | [EXPERIMENTAL] InsertExternalLogs: Inserts external logs into the specified ExternalApp Integration instance execution |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<LogsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LogsApi>();
```

---

<a id="getintegrationlogresults"></a>
## GetIntegrationLogResults

> PagedResourceListOfIIntegrationLogResponse GetIntegrationLogResults(string? filter = null, List<string>? sortBy = null, int? limit = null, string? pageToken = null)

[EXPERIMENTAL] GetIntegrationLogResults: Get integration log results

Get integration log results

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LogsApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 100;  // int? (optional)
var pageToken = "\"\"";  // string? (optional)
PagedResourceListOfIIntegrationLogResponse result = apiInstance.GetIntegrationLogResults(filter, sortBy, limit, pageToken);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Default: `100` |
| **pageToken** | **string?** | query | optional | The pagination token to use to continue listing integration logs; this value is returned from             the previous call. If a pagination token is provided, the &lt;i&gt;sortBy&lt;/i&gt; and &lt;i&gt;filter&lt;/i&gt; fields must not have changed since the original request.             For more information, see https://support.lusid.com/knowledgebase/article/KA-01915. Default: `&quot;&quot;` |

### Return type

[PagedResourceListOfIIntegrationLogResponse](PagedResourceListOfIIntegrationLogResponse.md)

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
<summary>Using the GetIntegrationLogResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfIIntegrationLogResponse> response = apiInstance.GetIntegrationLogResultsWithHttpInfo(filter, sortBy, limit, pageToken);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="insertexternallogs"></a>
## InsertExternalLogs

> Object InsertExternalLogs(string instanceid, string runid, ExternalLogInsertionRequest externalLogInsertionRequest)

[EXPERIMENTAL] InsertExternalLogs: Inserts external logs into the specified ExternalApp Integration instance execution

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LogsApi>();
var instanceid = "instanceid_example";  // string
var runid = "runid_example";  // string
var externalLogInsertionRequest = new ExternalLogInsertionRequest(); // ExternalLogInsertionRequest
Object result = apiInstance.InsertExternalLogs(instanceid, runid, externalLogInsertionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceid** | **string** | path | **required** |  |
| **runid** | **string** | path | **required** |  |
| **externalLogInsertionRequest** | [ExternalLogInsertionRequest](ExternalLogInsertionRequest.md) | body | **required** |  |

### Return type

**Object**

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the InsertExternalLogsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Object> response = apiInstance.InsertExternalLogsWithHttpInfo(instanceid, runid, externalLogInsertionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

