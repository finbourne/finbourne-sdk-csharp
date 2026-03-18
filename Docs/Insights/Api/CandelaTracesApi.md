# Finbourne.Sdk.Insights.Api.CandelaTracesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetTraceDiagram**](#gettracediagram) | **GET** `/insights/api/candelatraces/{traceId}/diagram` | [EARLY ACCESS] GetTraceDiagram: Get the diagram representation for a specific trace. |
| [**GetTraceLog**](#gettracelog) | **GET** `/insights/api/candelatraces/{traceId}` | [EARLY ACCESS] GetTraceLog: Get the log for a specific trace. |
| [**ListTraceEventLogs**](#listtraceeventlogs) | **GET** `/insights/api/candelatraces/{traceId}/events` | [EARLY ACCESS] ListTraceEventLogs: Get the trace event logs for a specific trace. |
| [**ListTraceLogs**](#listtracelogs) | **GET** `/insights/api/candelatraces` | [EARLY ACCESS] ListTraceLogs: Get the logs for traces. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Insights.Api;
using Finbourne.Sdk.Insights.Client;
using Finbourne.Sdk.Insights.Extensions;
using Finbourne.Sdk.Services.Insights.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CandelaTracesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CandelaTracesApi>();
```

---

<a id="gettracediagram"></a>
## GetTraceDiagram

> TraceDiagramResponse GetTraceDiagram(string traceId)

[EARLY ACCESS] GetTraceDiagram: Get the diagram representation for a specific trace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CandelaTracesApi>();
var traceId = "traceId_example";  // string
TraceDiagramResponse result = apiInstance.GetTraceDiagram(traceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **traceId** | **string** | path | **required** | The identifier of the trace. |

### Return type

[TraceDiagramResponse](TraceDiagramResponse.md)

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
<summary>Using the GetTraceDiagramWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TraceDiagramResponse> response = apiInstance.GetTraceDiagramWithHttpInfo(traceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettracelog"></a>
## GetTraceLog

> TraceLog GetTraceLog(string traceId)

[EARLY ACCESS] GetTraceLog: Get the log for a specific trace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CandelaTracesApi>();
var traceId = "traceId_example";  // string
TraceLog result = apiInstance.GetTraceLog(traceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **traceId** | **string** | path | **required** | The identifier of the request to obtain the log for. |

### Return type

[TraceLog](TraceLog.md)

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
<summary>Using the GetTraceLogWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TraceLog> response = apiInstance.GetTraceLogWithHttpInfo(traceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtraceeventlogs"></a>
## ListTraceEventLogs

> ResourceListOfTraceEventLog ListTraceEventLogs(string traceId, string? page = null)

[EARLY ACCESS] ListTraceEventLogs: Get the trace event logs for a specific trace.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CandelaTracesApi>();
var traceId = "traceId_example";  // string
var page = "page_example";  // string? (optional)
ResourceListOfTraceEventLog result = apiInstance.ListTraceEventLogs(traceId, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **traceId** | **string** | path | **required** | The identifier of the request to obtain the log for. |
| **page** | **string?** | query | optional |  |

### Return type

[ResourceListOfTraceEventLog](ResourceListOfTraceEventLog.md)

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
<summary>Using the ListTraceEventLogsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTraceEventLog> response = apiInstance.ListTraceEventLogsWithHttpInfo(traceId, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtracelogs"></a>
## ListTraceLogs

> ResourceListOfTraceLog ListTraceLogs(string? filter = null, string? sortBy = null, int? limit = null, string? page = null)

[EARLY ACCESS] ListTraceLogs: Get the logs for traces.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CandelaTracesApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
ResourceListOfTraceLog result = apiInstance.ListTraceLogs(filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about [filtering results from LUSID](https://support.lusid.com/filtering-results-from-lusid). |
| **sortBy** | **string?** | query | optional | Order the results by these fields. Use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. Multiple fields can be denoted by a comma e.g. -MyFieldName,AnotherFieldName,-AFurtherFieldName |
| **limit** | **int?** | query | optional | When paginating, only return this number of records. The minimum value is 0 and the maximum is 10000. |
| **page** | **string?** | query | optional | Encoded pagwwwwe string returned from a previous search result that will retrieve the next page of data. When this field is supplied, filter and sortby fields should not be supplied. |

### Return type

[ResourceListOfTraceLog](ResourceListOfTraceLog.md)

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
<summary>Using the ListTraceLogsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTraceLog> response = apiInstance.ListTraceLogsWithHttpInfo(filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

