# Finbourne.Sdk.Insights.Api.RequestsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetRequest**](#getrequest) | **GET** `/insights/api/requests/{id}/request` | GetRequest: Get the request content for a specific API request. |
| [**GetRequestLog**](#getrequestlog) | **GET** `/insights/api/requests/{id}` | GetRequestLog: Get the log for a specific API request. |
| [**GetResponse**](#getresponse) | **GET** `/insights/api/requests/{id}/response` | GetResponse: Get the response for a specific API request. |
| [**ListRequestLogs**](#listrequestlogs) | **GET** `/insights/api/requests` | ListRequestLogs: Get the logs for API requests. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RequestsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RequestsApi>();
```

---

<a id="getrequest"></a>
## GetRequest

> Request GetRequest(string id)

GetRequest: Get the request content for a specific API request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RequestsApi>();
var id = "id_example";  // string
Request result = apiInstance.GetRequest(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The identifier of the request to obtain the content for. |

### Return type

[Request](Request.md)

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
<summary>Using the GetRequestWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Request> response = apiInstance.GetRequestWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrequestlog"></a>
## GetRequestLog

> RequestLog GetRequestLog(string id)

GetRequestLog: Get the log for a specific API request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RequestsApi>();
var id = "id_example";  // string
RequestLog result = apiInstance.GetRequestLog(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The identifier of the request to obtain the log for. |

### Return type

[RequestLog](RequestLog.md)

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
<summary>Using the GetRequestLogWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RequestLog> response = apiInstance.GetRequestLogWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getresponse"></a>
## GetResponse

> Response GetResponse(string id)

GetResponse: Get the response for a specific API request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RequestsApi>();
var id = "id_example";  // string
Response result = apiInstance.GetResponse(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The identifier of the request to obtain the response for. |

### Return type

[Response](Response.md)

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
<summary>Using the GetResponseWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Response> response = apiInstance.GetResponseWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrequestlogs"></a>
## ListRequestLogs

> ResourceListWithHistogramOfRequestLog ListRequestLogs(string? filter = null, string? sortBy = null, int? limit = null, string? page = null, string? histogramInterval = null)

ListRequestLogs: Get the logs for API requests.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RequestsApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var histogramInterval = "histogramInterval_example";  // string? (optional)
ResourceListWithHistogramOfRequestLog result = apiInstance.ListRequestLogs(filter, sortBy, limit, page, histogramInterval);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about [filtering results from LUSID](https://support.lusid.com/filtering-results-from-lusid). |
| **sortBy** | **string?** | query | optional | Order the results by these fields. Use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. Multiple fields can be denoted by a comma e.g. -MyFieldName,AnotherFieldName,-AFurtherFieldName |
| **limit** | **int?** | query | optional | When paginating, only return this number of records. The minimum value is 0 and the maximum is 10000. |
| **page** | **string?** | query | optional | Encoded page string returned from a previous search result that will retrieve the next page of data. When this field is supplied, filter and sortby fields should not be supplied. |
| **histogramInterval** | **string?** | query | optional | Optional interval to use in a histogram of the returned values. If not provided, no histogram will be generated. |

### Return type

[ResourceListWithHistogramOfRequestLog](ResourceListWithHistogramOfRequestLog.md)

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
<summary>Using the ListRequestLogsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListWithHistogramOfRequestLog> response = apiInstance.ListRequestLogsWithHttpInfo(filter, sortBy, limit, page, histogramInterval);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

