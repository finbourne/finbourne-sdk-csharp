# Finbourne.Sdk.Luminesce.Api.MultiQueryExecutionApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelMultiQuery**](#cancelmultiquery) | **DELETE** `/honeycomb/api/MultiQueryBackground/{executionId}` | CancelMultiQuery: Cancel / Clear a previously started query-set |
| [**GetProgressOfMultiQuery**](#getprogressofmultiquery) | **GET** `/honeycomb/api/MultiQueryBackground/{executionId}` | GetProgressOfMultiQuery: View progress of the entire query-set load |
| [**StartQueries**](#startqueries) | **PUT** `/honeycomb/api/MultiQueryBackground` | StartQueries: Run a given set of Sql queries in the background |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Luminesce.Api;
using Finbourne.Sdk.Luminesce.Client;
using Finbourne.Sdk.Luminesce.Extensions;
using Finbourne.Sdk.Services.Luminesce.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<MultiQueryExecutionApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
```

---

<a id="cancelmultiquery"></a>
## CancelMultiQuery

> BackgroundQueryCancelResponse CancelMultiQuery(string executionId)

CancelMultiQuery: Cancel / Clear a previously started query-set

Cancel the query-set (if still running) / clear the data (if already returned) The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't exist and is not running. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var executionId = "executionId_example";  // string
BackgroundQueryCancelResponse result = apiInstance.CancelMultiQuery(executionId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |

### Return type

[BackgroundQueryCancelResponse](BackgroundQueryCancelResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the CancelMultiQueryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundQueryCancelResponse> response = apiInstance.CancelMultiQueryWithHttpInfo(executionId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getprogressofmultiquery"></a>
## GetProgressOfMultiQuery

> BackgroundMultiQueryProgressResponse GetProgressOfMultiQuery(string executionId)

GetProgressOfMultiQuery: View progress of the entire query-set load

View progress information (up until this point) for the entire query-set The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't exist and is not running. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var executionId = "executionId_example";  // string
BackgroundMultiQueryProgressResponse result = apiInstance.GetProgressOfMultiQuery(executionId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |

### Return type

[BackgroundMultiQueryProgressResponse](BackgroundMultiQueryProgressResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetProgressOfMultiQueryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundMultiQueryProgressResponse> response = apiInstance.GetProgressOfMultiQueryWithHttpInfo(executionId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="startqueries"></a>
## StartQueries

> BackgroundMultiQueryResponse StartQueries(MultiQueryDefinitionType type, string body, DateTimeOffset? asAt = null, DateTimeOffset? effectiveAt = null, int? limit1 = null, int? limit2 = null, string? input1 = null, string? input2 = null, string? input3 = null, int? timeoutSeconds = null, int? keepForSeconds = null)

StartQueries: Run a given set of Sql queries in the background

 Allow for starting a potentially long running query and getting back an immediate response with how to  - fetch the data in various formats (if available, or if not simply being informed it is not yet ready), on a per result basis - view progress information (up until this point), for all results in one go - cancel the queries (if still running) / clear the data (if already returned)  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - there was something wrong with your query syntax (the issue was detected at parse-time) - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var type = Instrument;  // MultiQueryDefinitionType
var body = Apple;  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit1 = 56;  // int? (optional)
var limit2 = 56;  // int? (optional)
var input1 = "input1_example";  // string? (optional)
var input2 = "input2_example";  // string? (optional)
var input3 = "input3_example";  // string? (optional)
var timeoutSeconds = 1200;  // int? (optional)
var keepForSeconds = 7200;  // int? (optional)
BackgroundMultiQueryResponse result = apiInstance.StartQueries(type, body, asAt, effectiveAt, limit1, limit2, input1, input2, input3, timeoutSeconds, keepForSeconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **MultiQueryDefinitionType** | query | **required** | An enum value defining the set of statements being executed |
| **body** | **string** | body | **required** | A \&quot;search\&quot; value (e.g. &#39;Apple&#39; on an instrument search, a &#x60;Finbourne.Filtering&#x60; expression of Insights, etc.) In the cases where \&quot;Nothing\&quot; is valid for a &#x60;Finbourne.Filtering&#x60; expression, pass &#x60;True&#x60;. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt time used by any bitemporal provider in the queries. |
| **effectiveAt** | **DateTimeOffset?** | query | optional | The EffectiveAt time used by any bitemporal provider in the queries. |
| **limit1** | **int?** | query | optional | A limit that is applied to first-level queries (e.g. Instruments themselves) |
| **limit2** | **int?** | query | optional | A limit that is applied to second-level queries (e.g. Holdings based on the set of Instruments found) |
| **input1** | **string?** | query | optional | A value available to queries, these vary by &#39;type&#39; and are only used by some types at all. e.g. a start-date of some sort |
| **input2** | **string?** | query | optional | A second value available to queries, these vary by &#39;type&#39; and are only used by some types at all. |
| **input3** | **string?** | query | optional | A third value available to queries, these vary by &#39;type&#39; and are only used by some types at all. |
| **timeoutSeconds** | **int?** | query | optional | Maximum time the query may run for, in seconds: &lt;0 → ∞, 0 → 1200s (20m) Default: `0` |
| **keepForSeconds** | **int?** | query | optional | Maximum time the result may be kept for, in seconds: &lt;0 → 1200 (20m), 0 → 28800 (8h), max &#x3D; 2,678,400 (31d) Default: `0` |

### Return type

[BackgroundMultiQueryResponse](BackgroundMultiQueryResponse.md)

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Accepted |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the StartQueriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundMultiQueryResponse> response = apiInstance.StartQueriesWithHttpInfo(type, body, asAt, effectiveAt, limit1, limit2, input1, input2, input3, timeoutSeconds, keepForSeconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

